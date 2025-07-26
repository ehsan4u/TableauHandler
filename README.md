# TableauHandler
A modular Python framework to automate and manage Tableau Server/Online resources and workflows.


 Python Project: Tableau Resource Manager (TRM)
A modular Python framework to automate and manage Tableau Server/Online resources and workflows.

📘 Project Overview
Description:
The Tableau Resource Manager (TRM) is a Python-based automation toolkit that enables programmatic control over Tableau Server or Tableau Cloud. It leverages Tableau’s REST API and Metadata API to automate administrative, development, and monitoring tasks such as:

User and group provisioning

Site, project, and workbook management

Scheduled extract refreshes

Permissions and audit controls

Metadata extraction and lineage reporting

TRM allows organizations to scale Tableau governance, reduce manual intervention, and ensure consistency across their Tableau environments.

🎯 Key Features
Feature	Description
🔐 User & Group Management	Automate creation, updates, and removal of users and groups
📁 Project & Workbook Control	Create/update/delete projects, publish workbooks and data sources
🔄 Refresh Scheduling	Trigger or reschedule extract refreshes (Hyper extracts)
🧾 Audit & Metadata Reports	Extract usage, lineage, and workbook/datasource relationships
🛡️ Permissions Management	Set and audit user permissions for dashboards and projects
⚙️ CI/CD Integration	Promote content between dev/test/prod environments via code
🔍 Search & Tagging	Search/filter assets and apply custom metadata/tags
🧪 Validation Utilities	Detect broken extracts, missing fields, or unused dashboards

🛠️ Technologies Used
Category	Tools / Libraries
Language	Python 3.10+
APIs	tableauserverclient, GraphQL (Metadata API)
Auth	Personal Access Token (PAT), OAuth
Data Handling	pandas, requests, json
Logging	loguru, logging
CLI / Config	argparse, click, PyYAML
Scheduling	cron, Apache Airflow (optional)
Deployment	Docker, GitHub Actions (CI/CD)

📂 Sample Folder Structure
pgsql
Copy
Edit
tableau-resource-manager/
│
├── config/
│   └── tableau.yaml             # Connection info, site, server, token
│
├── src/
│   ├── auth/                    # Authentication and session handling
│   ├── users/                   # User/group management
│   ├── workbooks/              # Publish/update/delete workbooks
│   ├── datasources/            # Datasource extraction & refresh
│   ├── metadata/               # Metadata API queries (lineage, usage)
│   └── permissions/            # Assign/view permission models
│
├── tests/
│   └── test_users.py
│
├── cli.py                      # Entry point for CLI usage
├── requirements.txt
├── .env
└── README.md
🧪 Example Use Cases
Bulk add users to a Tableau site:

bash
Copy
Edit
python cli.py add-users --csv users.csv
Trigger extract refresh for a published datasource:

bash
Copy
Edit
python cli.py refresh-datasource --name "Sales Data" --project "Retail"
Generate a workbook usage report for audit:

bash
Copy
Edit
python cli.py report-usage --output usage_report.csv
Promote dashboard from Dev to Prod:

bash
Copy
Edit
python cli.py promote-content --source dev --target prod --project "HR Dashboards"
📈 Benefits
Reduce reliance on manual admin in Tableau Server or Online

Enforce consistent governance and security policies

Improve observability and audit readiness

Support agile dashboard and content promotion workflows

Scale Tableau usage without increasing administrative burden

🚀 Future Enhancements
Slack/email alerts for failed extracts or usage drops

Integration with ServiceNow or Jira for access requests

Web-based UI for admins and analysts

Lineage mapping with Power BI and other tools


