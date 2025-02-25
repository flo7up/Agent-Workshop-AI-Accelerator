# Azure AI Agent Tutorial

This repository demonstrates how to build an Azure AI Agent that uses the Bing Search API to fetch news articles and stores the results in Azure Blob Storage with a timestamped filename. The tutorial also guides you through setting up Azure AI Studio, deploying a model (e.g., GPT-4o-mini), and testing agents in the Agent Playground.

> **Note:** This tutorial has been tested with Python **3.11.5** and is configured for the **sweden_central** region.

---

## Table of Contents

- [Setup and Prerequisites](#setup-and-prerequisites)
- [Azure AI Studio and Model Deployment](#azure-ai-studio-and-model-deployment)
- [Azure Resources Setup](#azure-resources-setup)
- [Repository Setup and Environment](#repository-setup-and-environment)
- [Running and Testing the Code](#running-and-testing-the-code)
- [Extending Your Agent with Additional Tools](#extending-your-agent-with-additional-tools)
- [Security Considerations](#security-considerations)
- [Further Ideas and Next Steps](#further-ideas-and-next-steps)

---

## Setup and Prerequisites

1. **Python Installation:**  
   Install Python 3.11.5 on your machine.

2. **Azure CLI:**  
   Ensure you have the Azure CLI installed. Log in with:
   ```bash
   az login --tenant <your-tenant-id>
   ```

3. **Git:**  
   Make sure Git is installed to clone the repository.

---

## Azure AI Studio and Model Deployment

1. **Azure AI Studio Setup:**  
   - Set up Azure AI Studio with your Hub and Project.
   - Deploy at least one model (e.g., **GPT-4o-mini**). If you use a different model, adjust the name accordingly.
   - Use **sweden_central** for testing.
   - Once deployed, play in the playground by chatting with your model and executing agents in the Agent Playground.

2. **Deploying a Model:**  
   - In Azure AI Studio, navigate to your workspace.
   - Deploy your model (e.g., GPT-4o-mini) following the standard deployment process.
   - Verify that the model is active and available for testing in the playground.

---

## Azure Resources Setup

Before turning to the code, ensure you have the following Azure resources ready:

1. **Bing Search Resource:**  
   - Create a Bing Search resource in Azure.
   - Obtain the API key from the resource and copy it.

2. **Azure Blob Storage:**  
   - Create an Azure Blob Storage account.
   - Copy the connection string from your Blob Storage account.

3. **Azure AI Project Connection:**  
   - Obtain your Azure AI Project connection string from Azure AI Studio.
   - Copy this connection string for later use in the code.

---

## Repository Setup and Environment

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/azure-ai-agent-tutorial.git
   cd azure-ai-agent-tutorial
   ```

2. **Create a Virtual Environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment Variables:**  
   Create a `.env` file in the repository root with the following values (replace placeholders with your actual values):
   ```env
   BING_API_KEY=your_bing_api_key_here
   PROJECT_CONNECTION_STRING=your_project_connection_string_here
   AZURE_STORAGE_CONNECTION_STRING=your_storage_connection_string_here
   ```

---

## Running and Testing the Code

1. **Run the Code:**  
   Execute the Python script to run the agent and store news data in Azure Blob Storage:
   ```bash
   python your_script.py
   ```

2. **Verify Blob Storage:**  
   After running the code, verify that a new file with a timestamp (e.g., `news_YYYYMMDD_HHMMSS.json`) is created in your designated Blob Storage container.

3. **Agent Playground:**  
   Once your agent is running in Azure AI Studio, interact with it in the Agent Playground by sending messages and executing available tools.

---

## Extending Your Agent with Additional Tools

This tutorial is a starting point. Consider adding additional tools to extend your agent’s capabilities. For example:
- **Social Media Integration:**  
  Wrap APIs to fetch social media information.
- **Email Functionality:**  
  Integrate with an email service to send notifications.
- **Document Intelligence:**  
  Use Azure Document Intelligence to read and process PDFs.
- **SharePoint Search:**  
  Build a tool to search through SharePoint documents.
- **Code Interpreter:**  
  Integrate a code interpreter for data analysis and visualization.
- **SQL Database Interaction:**  
  Connect to a SQL database to execute queries and retrieve data.

Each tool should be a narrow wrapper around a specific API. This design reduces complexity and improves performance.

---

## Security Considerations

- **Action Permissions:**  
  Ensure that your agent’s actions do not unintentionally expose or modify sensitive data.
- **API Wrappers:**  
  Design tools with the principle of least privilege in mind.
- **Risk Management:**  
  Agents may be autonomous or require human approval when handling challenging cases. Evaluate the security implications of automated actions, especially those affecting customer data.

---

## Further Ideas and Next Steps

- **Autonomous vs. Interactive Agents:**  
  Agents can either be fully autonomous, interact with users, or operate with human oversight when necessary.
- **Performance Tuning:**  
  The performance of your agent is heavily influenced by how you design its tools. Narrow, purpose-built tools can reduce complexity.
- **Expand Use Cases:**  
  Consider expanding your agent’s capabilities with more integrations, such as IoT data processing or advanced data analytics.

---

Happy coding and experimenting with your Azure AI Agent!
