# Agentic AI
 
Hands-on notebooks exploring agentic AI systems — multi-agent orchestration, Model Context Protocol (MCP) tool use, and the GPU/ML infrastructure (AMD ROCm) that powers local LLM inference for these agents.
 
## Contents
 
| Notebook | Description | Key tools/frameworks |
|---|---|---|
| [`Tutorial_Powering_Google_ADK_on_AMD_Platform_and_Local_LLMs.ipynb`](./Tutorial_Powering_Google_ADK_on_AMD_Platform_and_Local_LLMs.ipynb) | Builds a real-world Agent-to-Agent (A2A) system — a "Purchasing Concierge" that coordinates a Burger Seller agent and a Pizza Seller agent under a root purchasing agent — running on AMD Instinct GPUs. | Google ADK, A2A protocol, CrewAI, LangChain/LangGraph, vLLM, Ollama, Gradio |
| [`build_airbnb_agent_mcp.ipynb`](./build_airbnb_agent_mcp.ipynb) | Workshop building an AI agent that connects to external tools via the Model Context Protocol (MCP), served locally through vLLM on an AMD MI300X GPU. | Pydantic AI, MCP, vLLM |
| [`Lab_3_Libraries_PyTorch__3_.ipynb`](./Lab_3_Libraries_PyTorch__3_.ipynb) | ROCm Certification Program (Level 1) lab covering the GPU compute libraries underneath these agent stacks: rocBLAS GEMM benchmarking, MIOpen convolution autotuning, and PyTorch-on-ROCm verification. | PyTorch (ROCm/HIP), rocBLAS, MIOpen |
 
## Why these are grouped together
 
The first two notebooks show agentic AI systems from two different angles — multi-agent-to-agent orchestration (Google ADK/A2A) and single-agent tool use via MCP (Pydantic AI) — both served by local, open-weight LLMs (vLLM/Ollama) instead of hosted APIs. The third notebook is the supporting infrastructure layer: verifying and benchmarking the AMD ROCm/PyTorch stack that those local models run on.
 
## Getting started
 
Each notebook is self-contained with its own setup cells (repo clones, `pip install`s, and model server instructions). In general:
 
1. **Serve a local LLM** — the tutorials use [vLLM](https://github.com/vllm-project/vllm) and/or [Ollama](https://ollama.com/) to serve open-weight models (e.g. Llama 3.1) on AMD GPUs.
2. **Install notebook dependencies** — each notebook installs its own packages (`crewai`, `google-adk`, `pydantic-ai-slim[mcp]`, `langgraph`, `gradio`, etc.) in its early cells.
3. **Run cells top to bottom** — cells that spawn a model server expect that server to be started in a separate terminal first (instructions are inline).
### Requirements
 
- Access to an AMD GPU (Instinct/MI-series) with ROCm installed for the AMD-specific tutorials, or any GPU/CPU capable of running vLLM/Ollama for the agent notebooks
- Python 3.10+
- A Hugging Face token (`HF_TOKEN`) if pulling gated models like Llama 3.1
## Notes
 
- These notebooks originate from AMD/Google developer workshops and certification material, adapted here as a personal reference for agentic AI patterns (A2A multi-agent systems, MCP tool-calling agents) on local/open-source model infrastructure.
- Update the `BASE_URL`, ports, and model names in each notebook to match your own local server setup.
 
