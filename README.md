# SOC-Automation
##  Overview
This project demonstrates how AI-powered automation can streamline Security Operations Center (SOC) workflows.  
Using **n8n**, **Ollama**, **Splunk**, and **Slack**, the setup enables autonomous alert processing and decision-making, essentially turning a local LLM into an **AI security agent**.

Since this setup is completely local, it removes the privacy risk that comes with feeding data into an API accessesed LLM?

---

## Components
- **n8n:** Workflow automation platform for orchestrating alert handling and actions.  
- **Splunk:** SIEM platform used for log collection, analysis, and alert generation.  
- **Ollama:** Local LLM runtime for processing alerts and making decisions based on their context.  
- **Slack:** Communication channel for outputting automated responses and notifications.  
- **Windows 10 VM:** Simulated endpoint generating security logs for Splunk.

---

## Project Architecture
1. **Splunk** detects suspicious activity and triggers an alert.  
2. The alert is forwarded to **n8n** via webhook or API call.  
3. **Ollama** receives the alert content, analyzes it, and classifies it (e.g., *low*, *medium*, *high severity*).  
4. Based on the decision, **n8n** carries out automated actions such as:
   - Sending alerts to **Slack**.
   - Executing response workflows (e.g., disabling a user, isolating a host).
5. The process forms a closed-loop SOC automation system capable of intelligent, context-aware responses.

---

## 🧰 Setup Steps
1. **Install and configure n8n**
   - Create a workflow to receive Splunk alerts and interact with Ollama and Slack.
2. **Set up Splunk**
   - Configure alert rules and webhooks for automation triggers.
3. **Deploy Ollama**
   - Install Ollama locally.
   - Pull and configure a model (e.g., Llama 3, Mistral) for decision-making tasks.
4. **Set up Slack**
   - Create a bot or webhook for automated notifications.
5. **Integrate components**
   - Test full alert-to-response flow and validate the automation.

---

## Example Workflow
- **Input:** Splunk detects repeated failed login attempts.  
- **Process:** Alert sent to n8n → analyzed by Ollama → determined as brute-force attempt.  
- **Output:** n8n notifies Slack and triggers response action (e.g., lock user account).

---

## Future Enhancements
- Add threat enrichment using OSINT APIs (e.g., VirusTotal, AbuseIPDB).  
- Integrate ticketing (e.g., TheHive or Jira).  
- Train a fine-tuned model for better incident classification.  
- Add natural language summaries for incident reports.

---

## 🧑‍💻 Author
**Obah Emmanuel (EOLO)**  
Cybersecurity Engineer | SOC & Cloud Security Enthusiast  
[LinkedIn](https://www.linkedin.com/in/emmanuel-obah-8a0521333/) • [GitHub](https://github.com/obah2008)

---

