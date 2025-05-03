# RAG-vs-CAG-vs-AgenticRAG
## Overview
This repository contains demonstration workflows and notebooks showcasing three techniques—Retrieval‑Augmented Generation (RAG), Cache‑Augmented Generation (CAG), and Agentic RAG—applied in n8n and Jupyter environments. 

These demos illustrate how each approach handles context management and external knowledge integration to enhance large language model outputs.  


## Contents
1. Agentic_RAG_cooking_game.json  
An n8n workflow demonstrating an Agentic RAG pipeline that uses AI agents to autonomously choose between retrieval and caching for a cooking assistant scenario. 
  

2. RAG_cooking_game.json  
An n8n workflow implementing pure Retrieval‑Augmented Generation (RAG) for the same cooking assistant use case. 

3. CAG/

  - *Cache_Augmented_Generation.ipynb*  
A Jupyter notebook illustrating Cache‑Augmented Generation (CAG) by preloading recipe data into the model’s context window for instant recall. 
  
  - *moroccan_meals.txt*  
A plain text file containing sample Moroccan meal descriptions and step‑by‑step cooking instructions used as the CAG dataset. 
  
## Requirements
- n8n v0.204.0+ (self‑hosted via Docker or n8n cloud)  
- Python ≥ 3.8 (to run the notebook)   
- Jupyter Notebook or JupyterLab (for .ipynb execution)   


## Setup  
1. Import n8n workflows  

```bash
n8n import:workflow --input=Agentic_RAG_cooking_game.json  
n8n import:workflow --input=RAG_cooking_game.json  
```

2. Install Python dependencies

```bash
pip install jupyter openai  
```

3. Launch the notebook

```bash
jupyter notebook CAG/Cache_Augmented_Generation.ipynb  
```

## Usage
- RAG Workflow: Executes a cooking Q&A by retrieving relevant recipe steps from a vector store (FAISS) and feeding them to the LLM.   

- Agentic RAG Workflow: Demonstrates an AI “controller” agent that routes queries to either the retrieval agent or cache agent based on predefined rules.   

- CAG Notebook: Preloads Moroccan meal recipes into the LLM’s context window, enabling sub‑5 ms response times without external retrieval.  
