# 📬 Gmail Send Workflow using n8n + LangChain + Gemini

This repository contains an automated workflow for **sending Gmail messages** based on chat input using **n8n**, **LangChain**, and **Google Gemini API**.

## 🚀 Workflow Summary

This n8n workflow does the following:
1. **Listens for chat input** via a LangChain trigger.
2. **Uses a conversational agent** to analyze the input.
3. **Cleans personal data** from the chat (masking emails, names, birthdates, etc.).
4. **Processes with Google Gemini model** (via LangChain's integration).
5. **Stores memory temporarily** to maintain conversation context.
6. **Sends an email via Gmail** with a custom subject and message.

## 🔧 Requirements

- [n8n](https://n8n.io/)
- Google Gemini API Key (configured in n8n credentials)
- Gmail account with OAuth2 credentials (also set in n8n)
- LangChain integration enabled in n8n

## 🧠 Main Nodes in the Workflow

| Node Name                  | Purpose                                                 |
|---------------------------|---------------------------------------------------------|
| When chat message received| Triggers the workflow on chat input                    |
| Agent                     | Handles AI logic, masking sensitive info               |
| Google Gemini Chat Model  | Processes input with Gemini for response generation    |
| Simple Memory             | Stores short-term memory (context window = 10)         |
| Send a message in Gmail   | Sends a response email to a configured address         |
| Sticky Note               | Developer note to initiate the flow manually           |

## 🔐 Credentials Setup

1. **Google Gemini API Key**  
   - Create API credentials via [Google AI Studio](https://makersuite.google.com/).
   - Add in n8n: *Google Gemini(PaLM) API account*

2. **Gmail OAuth2**  
   - Set up your Gmail OAuth credentials in Google Cloud Console.
   - Add in n8n as: *Gmail account 6*

## ⚙️ How to Use

1. Clone this repository.
2. Import the `Gmail send.json` file into your n8n instance.
3. Ensure all credentials are set up in n8n.
4. Start the workflow manually or trigger it via the chatbot.
5. Confirm that the email is sent successfully to your target address.

