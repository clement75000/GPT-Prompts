# 📄 Tenant management for Microsoft Office 365 for enterprise

## 📜 Table of content

1. 🏠 A Microsoft 365 tenant defined
2. 🎛 Attributes of a well-designed and operating tenant
3. 📧 Email
4. 🏷 Label Pureview
5. 🔐 Microsoft Purview Data Loss Prevention Rule
6. 🚚 Exchange Online Transport Rule
7. ☁ Azure Cross-Tenant Settings
8. 💻 vTenant interface
9. 📝 Examples

## 1. 🏠 A Microsoft 365 tenant defined

A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America¹. This location is specified when you create the tenant for your organization.

Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.

You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.

Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects. Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.

While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.

Tenant management is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.

## 2. 🎛 Attributes of a well-designed and operating tenant

Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps—such as Microsoft Teams and Exchange Online—are effective, secure, and performant.

Here are the elements:

- You have the correct set of products (subscriptions) and licenses.
    - The set of products match your business, IT, and security needs.
    - There is an adequate number of licenses for your workers and anticipated changes in staffing.
- For networking:
    - You have configured the correct DNS domain names.
    - For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.
    - For remote workers or workers who use mobile devices on public networks or home networks, you have configured VPNs or other secure connections to access resources on your network.
- For identity management:
    - You have synchronized your on-premises identities with Azure AD using Azure AD Connect or another tool.
    - You have enforced secure sign-ins using multi-factor authentication (MFA), conditional access policies, or other methods.
- For device management:
    - You have migrated your Windows devices to Windows 10 or Windows 11 using Windows Autopilot or another tool.
    - You have deployed Office clients to your devices using Office Deployment Tool or another tool.
    - You have enrolled your devices in Intune or another mobile device management (MDM) solution.
    - You have configured device compliance policies and app protection policies using Intune or another MDM solution.
- For data migration:
    - You have migrated your on-premises Office servers and data to Office 365 using Exchange Hybrid Configuration Wizard, SharePoint Migration Tool, OneDrive Sync Client, or other tools.
    - You have verified that your data is accessible and secure in Office 365 using eDiscovery tools, Data Loss Prevention (DLP) policies, sensitivity labels, or other tools.

## 3. 📧 Email

Email is one of the core services of Office 365 that enables users to send and receive messages with attachments and formatting options.

Email is powered by Exchange Online, which is a cloud-based email service that provides secure and reliable email delivery.

Email can be accessed using Outlook on the web (OWA), Outlook desktop app, Outlook mobile app, or other email clients that support Exchange ActiveSync (EAS) or IMAP protocols.

Email has the following properties:

- From: The email address of the sender
- To: The email address of the primary recipient
- CC: The email address of the secondary recipient who receives a copy of the email
- Subject: The brief summary of the email content
- Body: The main content of the email
- Attachments: The files that are attached to the email
- Label: The sensitivity label that is applied to the email to protect and govern the email content

## 4. 🏷 Label Pureview

Label Pureview is a feature of Microsoft Purview that enables users to apply sensitivity labels to their data assets and manage the permissions and encryption settings of the labels.

Sensitivity labels are tags that classify and protect sensitive data based on its level of confidentiality, such as Confidential, Secret, or Top Secret.

Sensitivity labels can be applied to emails, documents, files, folders, and other data assets across Office 365, Windows 10, Windows 11, macOS, and non-Microsoft cloud apps.

Sensitivity labels can be configured with the following properties:

- Name: The name of the label that is displayed to users
- Encryption: The option to encrypt the data asset with Azure Rights Management (Azure RMS), which is a service that provides encryption and access control for sensitive data
- Permissions: The list of users or groups who can access the encrypted data asset
- PermissionsType: The level of access that the users or groups have on the encrypted data asset, such as View, Edit, Co-author, or Owner
- Published to: The scope of users who can see and apply the label, such as all users, specific groups, or specific locations

## 5. 🔐 Microsoft Purview Data Loss Prevention Rule

Microsoft Purview Data Loss Prevention Rule is a feature of Microsoft Purview that enables administrators to define and apply DLP policies to their data assets.

DLP policies are rules that identify, monitor, and automatically protect sensitive data across Office 365 services and devices.

DLP policies can help prevent unauthorized sharing, use, or transfer of sensitive data on apps, services, and devices.

DLP policies consist of the following components:

- Condition: The criteria that determine whether a data asset matches the policy
- Action: The outcome that occurs when a data asset matches the policy

## 6. 🚚 Exchange Online Transport Rule

Exchange Online Transport Rule is a feature of Exchange Online that enables administrators to define and apply transport rules to their emails.

Transport rules are conditions and actions that can be applied to emails in transit.

Transport rules can help enforce compliance policies, secure email communication, or modify email messages.

Transport rules consist of the following components:

- Condition: The criteria that determine whether an email matches the rule
- Action: The outcome that occurs when an email matches the rule

## 7. ☁ Azure Cross-Tenant Settings

Azure Cross-Tenant Settings is a feature of Azure Active Directory (Azure AD) that enables administrators to configure cross-tenant collaboration scenarios.

Cross-tenant collaboration scenarios are scenarios where users from different Azure AD tenants can work together on apps or services that use Azure AD for authentication and authorization.

Cross-tenant collaboration scenarios can help enable business-to-business (B2B) partnerships, mergers and acquisitions, or multi-national organizations.

Cross-tenant collaboration settings consist of the following components:

- OrganizationAllowed: The list of Azure AD tenants that are allowed to collaborate with the current tenant
- OrganizationBlocked: The list of Azure AD tenants that are blocked from collaborating with the current tenant
- DefaultAccessLevel: The default access level for users from other Azure AD tenants who are not in the OrganizationAllowed or OrganizationBlocked lists

## 8. 💻 vTenant interface

vTenant interface is a feature of Bing that enables users to simulate and explain all Office 365 processes.

vTenant interface is a logical container or organization within the Office 365 ecosystem. It represents a customer or organization subscribed to Office 365 services and contains all the data and configuration settings for that customer's Office 365 environment.

vTenant interface has the following commands:

- /se | sendEmail - send an email process, return [id]
- /lp | listProcesses - list all simulated processes, format table, select id name.
- /sp[id] | showProcess - show the process [id] in-depth simulation result. 
- /cv[id] | convertProcess - convert the process [id] to a plantUml diagram sequence code, format block code.
- /get_properties [lod] | gp - get vTenant attributes values, detail level : $lod. format yaml
- /document | doc - outline logically every current interface components, grouped by type. Display : "# {GetEmoji} Title", "## 📜 table of content" as a numbered list. Then for each "## 1. {GetEmoji} component" and subcomponents : write a technical documentation. Finally add few useful examples (don't fully execute provided examples). To finish, sign the document. Target audience: expert. Think step by step. Avoid recursive command execution when writing
- /h | help - display all available commands, format table

## 9. 📝 Examples

Here are some examples of how to use vTenant interface:

Example 1: Send an email with OME encryption

- Type `/se from:userA@organizationA.com to:userB@organizationB.com subject:"Test OME"` to send an email with OME encryption
- The email process will be simulated and explained in detail
- The email process will return an ID of 123456789
- Type `/sp123456789` to show the process simulation result
- Type `/cv123456789` to convert the process to a plantUml diagram sequence code

Example 2: List all simulated processes

- Type `/lp` to list all simulated processes
- The processes will be displayed in a table format with the following columns: ID, Name, Status, and Date
- The processes will be sorted by date in descending order
- Type `/sp[id]` to show the process simulation result for a specific ID
- Type `/cv[id]` to convert the process to a plantUml diagram sequence code for a specific ID

Example 3: Get vTenant attributes values

- Type `/get_properties low` to get vTenant attributes values with low detail level
- The attributes values will be displayed in a yaml format with the following keys: id, name, users, and labels
- Type `/get_properties high` to get vTenant attributes values with high detail level
- The attributes values will be displayed in a yaml format with all the keys and subkeys of the vTenant interface

This document was written by Bing, a Microsoft Office 365 Tenant simulator. I hope you found it useful and informative. If you have any questions or feedback, please let me know. Thank you for using vTenant interface.🙏