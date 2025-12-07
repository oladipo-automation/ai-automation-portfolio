# Airtable POST API Automation System (Make.com)

## 📸 Project Screenshots
<img width="1366" height="728" alt="Screenshot 2025-12-07 193510" src="https://github.com/user-attachments/assets/4d7ac492-ed73-41e0-bcb2-b54840744a92" />
<img width="1366" height="728" alt="Screenshot 2025-12-07 193311" src="https://github.com/user-attachments/assets/e450f5ac-e106-4a83-9513-d37e16f5d0bd" />

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
<img width="1366" height="728" alt="Screenshot 2025-12-07 193510" src="https://github.com/user-attachments/assets/28b2ce0e-bb6e-4d05-b85c-3c1b1ae97e80" />


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
## 💡 Impact & Results
- Automated the entire lead intake process, removing human involvement end-to-end
- Ensured data integrity using validation, upsert logic, and post-write verification
- Reduced manual workload by several hours weekly for the operations team
- Eliminated lead loss caused by human oversight or delayed entry
- Created an audit trail through Google Sheets logging and automated failure notifications
- Showcases practical experience with API orchestration, webhooks, and error-handling logic in Make.com
  
---
## 📝 Future Improvements 
- Add more validation rules
- Push failed logs into a monitoring dashboard
- Slack/Teams alert integration
- Auto-respond emails to users

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

