# Usage Guidance

To see the key capabilities of this accelerator in action after completing the installation, follow the execution step guidance included below.

Note that the steps follow a sequence conducted by the following persona:

* **Maria**, an Account Executive at a tech firm.

Maria is working in her system of productivity in Microsoft Teams and engages with a Copilot Studio Agent to streamline her ability to get a signed NDA contract in place with her customer, to help expedite a sales opportunity she is pursuing.

## Usage Note
The Adaptive Card shown at the start (or restart) of a conversation offers three clickable options. The first two options currently both enable searching for and viewing of existing NDAs for a given organization, with no current difference in functionality. 

## Execution steps for Customer <> AI Agent interaction:

Acting as Maria, go to Microsoft Teams, and engage in a chat with the Contract Assistant agent. At any point, if you're prompted to require addtional permissions to run actions, please click **"Connect" > establish connections by hitting "Submit" > Once all connections are "Connected" > Go back to the chat and click "Retry".**

* **AI Agent**: Welcome to your AI Legal Contract Assistant. Here are the options I can assist you with today. Check if a customer has an NDA, Get information about an NDA, Create a new NDA
* **Maria**: Clicks on **Create a new NDA** (click this option from the Adaptive Card)
* **AI Agent:** Ok, let's create an NDA. In order to create the NDA, I'll need to collect some information. Once you've provided the information, I'll generate your NDA.
* **AI Agent:** What is the name of the second party to the agreement?
* **Maria**: Fabrikam
* **AI Agent:** I found one or more matching accounts. Please select an appropriate account. You can type **'start over'** at any time.
* **Maria**: Clicks on 'Confirm' for 'Fabrikam Residences' (please select that from the Adaptive Card).
* **AI Agent**: I could not find any existing NDAs for the selected organization.
* **Maria**:
  **Second Party Address:** 123 Main Street, Redmond, WA, 12456
  **Second Party Signatory Name**: (Customer Signatory Name)
  **Second Party Signatory Title**: Director of Operations
  **Second Party Signatory Email**: (Customer Signatory Email, or your own email address if testing)
  **Your Organization Contact Name**: (Your Name)
* **Maria**: Clicks on Submit
* **Maria**: Clicks on Proceed
* **AI Agent:** Your In Progress agreement can be found here:
* **AI Agent:** Presents an Adaptive Card with a link
* **Maria**: Clicks on View and saves the document to view it.
* **AI Agent**: Are you ready to send this document over for Fabrikam Residences's signature?
* **Maria**: Clicks on Yes.
* **AI Agent**: The document has been sent to (Customer Signatory Name) for their signature. I will notify you when the signing has been completed with a link to the document.
* ***At this stage, there is a persona switch where you act as the customer and check your email and get the document from Docusign for eSignature. Open the document > insert signature in the box with titled 'Sign' > Adopt & Sign > insert Date signed > Finish.***
* **AI Agent**: 
  * **NDA with Fabrikam Residences**
  * **AI Agent**: Executed
  * **AI Agent**: This document was executed on (today's date) by Adatum Inc.
  * **Deal Owner:** (Your Name)
  * **NDA Type:** Bilateral
  * **Contract ID:** NDA-XX
