# Airtable POST API Automation System (Make.com)

## 📸 Project Screenshots

---

## 🧩 Project Overview
This automation eliminates manual copying of website form submissions into Airtable. Previously, the team entered data manually — causing errors, delays, and missed leads. I built a fully automated pipeline using Make.com, Airtable API, Postman, and Google Sheets.

---

## 🚀 What the Automation Does
- Receives form submissions through a custom webhook  
- Validates and sanitizes incoming data  
- Upserts (create/update) records into Airtable  
- Verifies that the Airtable record updated successfully  
- Logs successful entries into Google Sheets  
- Sends automated failure alert emails when something goes wrong  

---

## 🔧 Tools & Technologies
- Make.com  
- Airtable API  
- Google Sheets  
- Postman  
- Webhooks (JSON payloads)

---

## ⚙️ Workflow Architecture


### 1. Webhook Trigger
Make receives a POST request at a custom webhook URL. During development, I used Postman to simulate the website sending data.

### 2. Data Validation
The data is checked for required fields and correct formatting.

### 3. Airtable Upsert
The Airtable module creates a new record or updates an existing one, ensuring no duplicates.

### 4. Delay + Verification Check
A short delay is added, then Airtable is queried to confirm the update was successful.

### 5. Logging
- Success → Logged into Google Sheets  
- Failure → Automated email sent to the internal team with error details  

---

## 📦 Sample Incoming Payload
```json
{
  "full_name": "Sarah Patel",
  "email": "s.patel@creativelabs.io",
  "phone": "+1 202 555 0132",
  "company": "Creative Labs",
  "inquiry_type": "Partnership",
  "message": "We’re exploring collaborations with automation consulting teams.",
  "submitted_at": "2025-12-01T09:12:44Z"
}

