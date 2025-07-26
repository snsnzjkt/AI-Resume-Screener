# 🧠 AI Resume Screener — n8n Automation

## Overview

This project is an AI-powered resume screening system built using **n8n**, **OpenAI's o3-mini model**, and **Google services**. It automates the process of receiving, parsing, evaluating, and storing applicant resumes — reducing the time needed to shortlist candidates.

---

## 🔧 Key Features

* 📩 **Email Integration**: Uses Gmail Trigger to watch for incoming emails with PDF or DOCX resume attachments.
* ☁️ **Cloud Upload**: Uploads and organizes resumes in a specified **Google Drive** folder.
* 📎 **File Type Detection**: Detects and sorts between Word and PDF files using a **Switch node**.
* 🔁 **Format Conversion**: Converts Word files to Google Docs for parsing.
* 📄 **Text Extraction**: Extracts resume content from PDFs or Google Docs.
* 📑 **Job Description Sync**: Downloads a pre-defined job description from Google Drive.
* 🤖 **LLM Evaluation**:

  * Uses **LangChain** with OpenAI's o3-mini model to analyze resumes.
  * Evaluates alignment with the job description based on strengths, weaknesses, risk/reward, and overall fit.
* 📊 **Structured Output**:

  * Parses LLM output using a defined schema.
  * Extracts candidate name and email via the `Information Extractor` node.
* 📈 **Google Sheets Logging**: Appends structured screening results to a Google Sheet for tracking applicants.

---

## 🔌 Tech Stack

* **Automation Engine**: n8n
* **AI Model**: OpenAI o3-mini (via LangChain node)
* **Storage**: Google Drive
* **Spreadsheet Logging**: Google Sheets
* **Input Sources**: Gmail (resume submissions)
* **Format Support**: PDF, DOCX (auto-converted to Google Docs)

---

## 📁 File Structure

* **`AI Resume Screener.json`** — n8n workflow export file
  Import into your n8n instance to recreate the workflow.

---

## ✅ Setup Instructions

1. **Credentials Required:**

   * Gmail OAuth2 (for email trigger)
   * Google Drive API
   * Google Sheets API
   * OpenAI API Key (via LangChain/OpenAI plugin)

2. **Import the Workflow:**

   * Log into your **n8n** instance.
   * Go to **Workflows > Import from File** and upload `AI Resume Screener.json`.

3. **Customize Nodes:**

   * Update Gmail trigger with your account.
   * Set correct folder ID in “Upload file” node.
   * Replace `job description` and `output sheet` URLs with your own resources.

4. **Activate the Workflow:**

   * Once credentials are configured, turn the workflow on.
   * Test by sending an email with a resume attachment.

---

## 📊 Output Sample (Google Sheets)

| Date       | First Name | Last Name | Email                                       | Strengths           | Weaknesses           | Risk Factor | Reward Factor | Overall Fit | Justification  |
| ---------- | ---------- | --------- | ------------------------------------------- | ------------------- | -------------------- | ----------- | ------------- | ----------- | -------------- |
| 2025-07-25 | Jane       | Doe       | [jane@example.com](mailto:jane@example.com) | Python, APIs, GPT-4 | No Twilio experience | Medium      | High          | 8           | Aligns well... |

---

## 📌 Use Cases

* HR & Recruitment Agencies
* Freelancers screening candidates for tech roles
* Startups automating hiring pipelines
* Educational platforms evaluating student resumes

---

## 🧠 Bonus Ideas

* Add Slack/Discord notification on new applicant
* Auto-reply to applicants with status update
* Track improvement metrics over time via charts

---

Let me know if you want this saved as a downloadable README.md or turned into a Notion doc!
