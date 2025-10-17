 # Setting Up Ollama as a Local LLM Server

## Overview
In this section of the SOC Automation Project, we’ll be setting up **Ollama**, a local large language model (LLM) runtime that allows you to run open-source models entirely offline.  
This setup enables your AI-driven SOC to process Splunk alerts, reason about threat data, and trigger automated workflows, all while maintaining **complete data privacy**.

## Setup
> This setup assumes the operating system you're running is windows

### Step 1: Download WSL
- On the powershell terminal download and install WSL[Windows Subsystem for Linux] using the command below
```pwsh
wsl --install
```
<img width="1364" height="717" alt="image" src="https://github.com/user-attachments/assets/179d9ad7-af0a-4e25-9add-7ba85bb40e09" />

- Setup a usename and password

### Step 2: Download and update packages
```bash
sudo apt update && sudo apt upgrade -y
```
### Step 3: Installing Ollama

Next, we’ll install **Ollama**, the local AI model runner that allows us to run open-source LLMs directly on our machine.  
Head over to the [Ollama Linux download page](https://ollama.com/download/linux) and run the following command in your WSL terminal:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```
<img width="1364" height="719" alt="image" src="https://github.com/user-attachments/assets/0ff70ecf-d978-4670-96c7-bec51739ef60" />

### Step 4: Pulling the LLM

Since Ollama by itself is just an engine, we’ll need to pull a Large Language Model (LLM) for this setup to actually function.  
For this project, I’ll be using **Mistral**, but there are several other great options depending on your system’s specs and use case.

| Model | Description | Command | Recommended Specs |
|:--|:--|:--|:--|
| **Mistral** | Balanced in size and performance, ideal for local automation tasks. | `ollama pull mistral` | 16 GB RAM, quad-core CPU |
| **Llama3:8b** | Slightly larger, more advanced reasoning, slower on weaker hardware. | `ollama pull llama3:8b` | 16 GB+ RAM, modern CPU |
| **Gemma:2b** | Lightweight model by Google, great for fast responses. | `ollama pull gemma:2b` | 8–12 GB RAM |
| **Phi3:mini** | Small and efficient Microsoft model, very fast on midrange laptops. | `ollama pull phi3:mini` | 8 GB RAM |
| **NeuralChat** | Tuned for conversational tone, useful for interactive tasks. | `ollama pull neural-chat` | 16 GB RAM |

To pull **Mistral**, run the following command:
```bash
ollama pull mistral
```

### Step 5: Setting up Web UI *(Optional)*

> **Note:** This step is completely optional, the Web UI is only for convenience.  
> Ollama will still work perfectly fine via the command line or API without it.

#### Installing Docker
Before installing the web UI, we'll need docker

#### ⚙️ Installing the Web UI
For this setup, we’ll use **Open WebUI**, one of the most popular and lightweight interfaces for Ollama.


> **Note:**  
> This section of the SOC Automation Project is based on [Network Chuck’s video guide on Ollama](https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s).  
