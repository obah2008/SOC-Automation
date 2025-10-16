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
<img width="1365" height="719" alt="image" src="https://github.com/user-attachments/assets/9d7d766d-4aaf-40aa-a285-89b3c1593994" />

- Setup a usename and password

### Step 2:

> **Note:**  
> This section of the SOC Automation Project is based on [Network Chuck’s video guide on Ollama](https://www.youtube.com/watch?v=Wjrdr0NU4Sk&t=158s).  
