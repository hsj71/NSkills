## Step-by-Step Implementation
Let's build our Agentic RAG system which uses Llama-index:

### Step 1: Install Dependencies
We will install the required packages and libraries for our system,

llama-index: For document retrieval and embeddings.
langchain: For agent and tool management.
langchain_community: Required for ChatOpenAI in LangChain 0.3.x.
openai: For LLM API access.
wikipedia: Optional tool for agent to search Wikipedia.
```
!pip install llama-index==0.9.41 langchain==0.3.27 langchain_community openai==1.101.0 wikipedia
```
### Step 2: Upload Documents and OpenAI API Key
We will upload some documents and files which our model can use. Files we are using here can be dowloded from here.

Creates a docs/ folder to store our knowledge documents.
Users can upload .txt files.
Example content can include notes, articles or any text relevant to queries.
To know how to extract OpenAI API key refer to: How to find and Use API Key of OpenAI.

```
import os
from google.colab import files

os.makedirs("docs", exist_ok=True)

uploaded = files.upload()
for filename in uploaded.keys():
    os.rename(filename, f"docs/{filename}")

print("Uploaded files:", os.listdir("docs"))

os.environ["OPENAI_API_KEY"] = "your_key_here"
```
### Step 3: Import Libraries
We will import the required libraries for system,

SimpleDirectoryReader: Load documents.
GPTVectorStoreIndex: Create vector-based index for retrieval.
LLMPredictor & ServiceContext: Wrap LLM for LlamaIndex.
ChatOpenAI: OpenAI GPT model for text generation.
Tool, initialize_agent, AgentType: Build agentic reasoning system.
ConversationBufferMemory: Maintain past conversation context for agent.
wikipedia: Tool for retrieving general knowledge.
```
from llama_index import SimpleDirectoryReader, GPTVectorStoreIndex, LLMPredictor, ServiceContext
from langchain.chat_models import ChatOpenAI
from langchain.agents import Tool, initialize_agent, AgentType
from langchain.memory import ConversationBufferMemory
import wikipedia
```
### Step 4: Build the LlamaIndex Retrieval System
We will build the LlamaIndex Retrieval System in which,

SimpleDirectoryReader: Reads all uploaded documents.
LLMPredictor: Wraps GPT-3.5-turbo to work with LlamaIndex.
GPTVectorStoreIndex: Converts documents into embeddings stored in a vector store.
query_engine: Returns top 3 most relevant documents for any query.
```
documents = SimpleDirectoryReader("docs/").load_data()

llm_predictor = LLMPredictor(llm=ChatOpenAI(
    temperature=0, model_name="gpt-3.5-turbo"))

service_context = ServiceContext.from_defaults(llm_predictor=llm_predictor)

index = GPTVectorStoreIndex.from_documents(
    documents, service_context=service_context)

query_engine = index.as_query_engine(
    retriever_mode="default", similarity_top_k=3)
```
### Step 5: Define Tools for Agent
We will define the tools that are available for the agent to use:

DocumentRetriever: Uses LlamaIndex to fetch relevant docs.
Calculator: Handles numeric queries.
Wikipedia: Fetches general knowledge not in uploaded docs.
Tools: Each tool is callable by the agent automatically.
```
def retrieve_docs(query: str) -> str:
    response = query_engine.query(query)
    return str(response)

def calculator(query: str) -> str:
    try:
        return str(eval(query))
    except:
        return "Cannot calculate that."

def wiki_search(query: str) -> str:
    try:
        return wikipedia.summary(query, sentences=2)
    except:
        return "No Wikipedia info found."

tools = [
    Tool(name="DocumentRetriever", func=retrieve_docs,
         description="Retrieve answers from uploaded documents."),
    Tool(name="Calculator", func=calculator,
         description="Solve mathematical expressions."),
    Tool(name="Wikipedia", func=wiki_search,
         description="Get Wikipedia summaries.")
]
```
### Step 6: Initialize Agent with Memory
We will initialize ConversationBufferMemory which is a short-term, in-session memory to the agent:

ConversationBufferMemory: Keeps track of past queries and responses.
AgentType.ZERO_SHOT_REACT_DESCRIPTION: Agent decides which tool to call without pre-training.
verbose=True: Shows reasoning steps in the output.
```
memory = ConversationBufferMemory(memory_key="chat_history")

agent = initialize_agent(
    tools=tools,
    llm=ChatOpenAI(temperature=0, model_name="gpt-3.5-turbo"),
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    memory=memory,
    verbose=True
)
```
### Step 7: Run the System
We run our system in which:

Users can interact with the agent.
Agent decides which tool to use, retrieves relevant info and generates answers.
Supports document queries, math calculations and Wikipedia search.
```
print("Agentic RAG is ready! Type 'exit' to stop.")

while True:
    query = input("You: ")
    if query.lower() in ["exit", "quit"]:
        break
    response = agent.run(query)
    print("Agent:", response)
```
---
