# Job Application Tracker Automation (n8n)

## Overview

This automated workflow is designed to streamline and enhance the tracking of job applications. Using **n8n**, it integrates **Gmail** and **Notion** to automatically capture job application emails, extract key information, and maintain a real-time, comprehensive job tracker within Notion.

By automating manual updates and eliminating duplicated entries, this solution improves job application management efficiency, allowing focus on interview preparation and career growth.

---

## How It Works

- **Watch Job Applications (Gmail Trigger):** Continuously monitors your Gmail inbox for new job application-related emails using an expanded keyword list like "applying", "submitted", "assessment", "unfortunately", "interview", "shortlisted", "rejected", and more.
- **Filter Job Email Only:** Uses a regex-based filter to capture various recruiter email phrasings and statuses efficiently.
- **Extract Application Data:** Improved regex and fallback logic extract Company (including fallback to sender email), Job Title (including custom patterns like Ref codes), Date Applied, and Status (with expanded keywords).
- **Find Matching Job Entry (Notion):** Queries Notion with filters on Company and Job Title to find existing applications, preventing duplicates.
- **Check If Entry Exists:** Routes data either to update existing entries or to create new ones.
- **Update Job Status & Create New Job Entry:** Handles respective Notion database row updates or insertions.

---

## Features

- **Automatic email detection:** No manual data entry.
- **Real-time status updates:** Captures outcomes like interviews and rejections from emails.
- **Avoids duplicates:** Matches by Company + Job Title to update existing records.
- **Customizable:** Adapt regex and Notion properties based on needs.
- **Scalable:** Integrate with other apps or dashboards for enhanced career analytics.

---

## Getting Started

### Requirements

- n8n instance (cloud or self-hosted)
- Gmail account with OAuth credentials
- Notion account with database set up for job tracking
- Basic understanding of n8n workflows and API credentials setup

### Setup Instructions

1. **Import Workflow**  
   Download and import `job-application-tracker-n8n.json` into your n8n editor.

2. **Set Credentials**  
   Go to each Gmail and Notion node and authenticate your credentials.

3. **Configure Notion Database**  
   Ensure Notion database has properties for:  
   - **Company** (Rich Text)  
   - **Job Title** (Title)  
   - **Date Applied** (Rich Text or Date)  
   - **Status** (Select with options: Applied, Interview, Assessment, Rejected)

4. **Adjust Regex (Optional)**  
   Modify the regex patterns in the "Extract Application Data" node if your email formats vary.

5. **Activate Workflow**  
   Set workflow status to active to start monitoring new job application emails live.

---

## How to Use

- Apply to jobs as usual.
- Relevant emails will automatically populate/update the Notion tracker.
- Monitor your job search in Notion with up-to-date statuses.

---

