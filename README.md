# Automate Your Newsletter with AI & n8n in Minutes!


## How It Works

This project automates the creation and sending of newsletters with AI. It uses n8n for workflow automation, integrates Google APIs with OAuth2 for access, and leverages AI to automate content creation.

<img width="1704" alt="Automation Workflow" src="https://github.com/user-attachments/assets/203ff15d-957f-4c17-90e5-50513a70c52c" />


## Prerequisites

- **Docker** and **Docker Compose** installed on your local machine.
- A **Google Cloud project** with OAuth2 credentials (for Google Docs or Google Sheets API access).
- **n8n** running in a Docker container for automating workflows.

## Setting Up

Follow these steps to set up your project and get everything running.

### 1. Clone this Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/NikhilSetiya/auto-newsletter.git
cd auto-newsletter

### 2. Create Google OAuth2 Credentials
	•	Go to Google Cloud Console.
	•	Create a new project or select an existing one.
	•	Enable Google Docs API (or any relevant Google APIs).
	•	Go to APIs & Services → Credentials → Create Credentials → OAuth Client ID.
	•	Set the Authorized Redirect URI to :http://localhost:5678/rest/oauth2-credential/callback
	•	Download the OAuth credentials (Client ID and Client Secret).


### 3. Configure Docker for n8n

Edit the docker-compose.yml file with the following:
	•	Replace your-secure-encryption-key with a secure encryption key (you can generate a random string).
	•	Set your Basic Auth username and password in N8N_BASIC_AUTH_USER and N8N_BASIC_AUTH_PASSWORD.


### 4. Start n8n Using Docker

Run the following command to start n8n with Docker Compose: docker-compose up -d

This will start the n8n instance on http://localhost:5678.



### 5. Create and Test the Workflow
	•	Upload the shared workflow into n8n.
	•	Configure and add Api's to Grok, SeprApi and OpenAI nodes in the workflow.
	•	Add New Google OAuth2 Credentials:
	•	•	Paste Client ID and Client Secret from your Google Cloud project.
		•	Set the Redirect URI to http://localhost:5678/rest/oauth2-credential/callback.
	•	Click Save and Authenticate
	•	Click on test workflow and troubleshoot if you get an errors.




### 6. The Newsletter is saved in the drive
	•	Open your drive and go the folder path provided in the n8n workflow and you can find your newsletter.


## Troubleshooting
	•	If you face issues with OAuth2 authentication, ensure that the Redirect URI is correct both in Google Cloud Console and in n8n.
	•	If n8n is not running as expected, try restarting the container: docker-compose restart


