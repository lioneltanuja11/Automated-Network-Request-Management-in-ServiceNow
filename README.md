# Automated-Network-Request-Management-in-ServiceNow
This project focuses on automating network-related service requests using the ServiceNow platform. It streamlines the process of handling user requests such as network access, permissions, and approvals through a structured and automated workflow system.  The goal is to reduce manual intervention, improve efficiency.

This project focuses on automating network-related service requests using the ServiceNow platform. It simplifies and streamlines the process of handling requests such as network access, permissions, and approvals through a structured workflow system.

The system minimizes manual effort, reduces delays, and improves operational efficiency by automating request routing, approvals, and task assignments.

🎯 Objectives
Automate repetitive network request processes
Reduce manual errors and processing time
Improve transparency and request tracking
Enhance user experience with a structured system
⚙️ Features
📥 Service Catalog for request submission
🔐 Role-Based Access Control (RBAC)
🔄 Automated approval workflows
👥 Dynamic assignment groups (Admin, Approver, Network Team, Requester)
🔔 Email/notification system for updates
📊 Centralized request tracking
🏗️ System Architecture

The system is built using core ServiceNow modules:

Service Catalog – Interface for users to submit requests
Flow Designer / Workflow Editor – Automates approval process
User & Group Management – Defines roles and responsibilities
Access Control (ACLs) – Ensures secure data handling
🔄 Workflow Process
User submits a request via Service Catalog
Request is sent to the Approver
Once approved, it is assigned to the Network Team
Task is executed and updated in the system
Request is closed and user is notified
🛠️ Technologies Used
ServiceNow Platform
IT Service Management (ITSM)
Workflow Automation
Access Control Mechanisms
📂 Project Structure
📁 Automated-Network-Request-Management
 ┣ 📄 README.md
 ┣ 📂 Screenshots
 ┣ 📂 Workflows
 ┣ 📂 Documentation
📸 Screenshots

1. Functional Overview
Purpose: Explains what the app does for the business.

📝 Functional Overview
The Automated Network Request System streamlines the process for employees to request network changes (Firewall, VPN, Port access).

Core Variables Captured:

Request Type, Justification, Device Details, and Urgency.

Approval Workflow:

Standard: Automatically routes to the Requester's Manager.

High-Sensitivity: Routes to the Network Security Group for secondary validation.

Department-Specific: Ensures correct stakeholder oversight based on the selected assignment group.

2. Technical Blueprint
Purpose: Explains how the app was built (The "Architecture").

🏗️ Technical Blueprint
System Architecture:

Catalog Item: Network Request (Portal-facing).

Custom Tables: >     * u_network_database: Stores historical request data.

u_network_task: Manages sub-tasks for technical fulfillment.

Flow Designer Logic:

Triggered on Service Catalog submission.

Mapping: Catalog variables are dynamically mapped to custom table fields using "Create Record" actions.

Conditional Branching: Uses If/Else logic to handle Manager approvals and trigger automated email notifications.

Security (ACLs):

Restricted Write access to the Work Status field to ensure data integrity; only the System Flow can update the status upon approval.

3. Setup Manual
Purpose: A "How-to" guide for other developers to recreate your work.

⚙️ Setup & Installation Manual
Follow these steps to deploy this solution in a new PDI:

Table Creation: Create u_network_database. Ensure columns match the captured variables.

Catalog Configuration: Create the Network Request Catalog Item. Map variables to the table using the "Variable Name" field.

Flow Designer: >    * Import/Build the Network Request Flow.

Set the "Ask for Approval" action to dot-walk to Opened by.Manager.

Access Control: Create a Record level Write ACL for your table. Add the admin or itil role.

Testing: Submit a test through the Service Portal and verify the "Executions" tab in Flow Designer.

🚀 How It Works
Users raise requests through the catalog
System automatically routes requests based on roles
Approvals are handled digitally
Tasks are assigned without manual intervention
📈 Future Enhancements
🤖 AI-based request prediction and routing
📊 Dashboard for analytics and reporting
🌐 Integration with real-time network systems
📱 Mobile-friendly interface
💡 Learning Outcomes
Hands-on experience with ServiceNow platform
Understanding of ITSM workflows
Implementation of RBAC and automation
Real-world enterprise workflow design
👩‍💻 Author

Lionel Tanuja
Final Year ECE Student | Tech Enthusiast | ServiceNow Learner
