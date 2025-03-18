# Pre Requisites

* Power Platform environment with Dataverse enabled and System Administrator access.
* Copilot Studio license.
* DocuSign license/ trial.
* Access to create a SharePoint site.

# Deployment Guide

This document will comprise of step by step instructions on how to deploy this solution. At a very high level, it has 3 major setups involved.

1. SharePoint Site setup
2. DocuSign Setup
3. Copilot Agent Setup

# Step 1: SharePoint Setup

This will be a manual step as the Power Platform solution does not include a SharePoint site. This site is needed to store the NDA agreement contracts which are created but pending signature and the signed contracts as well.

## Step 1.1: Create SharePoint site

1. Go to (https://(your tenant).sharepoint.com/) and click **'Create site'.**
2. Select **Team Site.**
3. Select **Standard Team** template.
4. Enter name as desired.
5. **Save the URL** of this SharePoint site which will be used later to update environment variables. This will be in the format of: https://(your tenant).sharepoint.com/sites/(site name).

## Step 1.2: Create SharePoint Document Libraries

1. Create a new [SharePoint document library](https://support.microsoft.com/en-us/office/create-a-document-library-in-sharepoint-306728fe-0325-4b28-b60d-f902e1d75939#ID0EBF=Modern) and name it as desired, for example, "UnsignedDocumentsandTemplates". This library will be used to store the templates documents of the NDA and the NDA documents sent to customer but not signed yet.
2. Create 2 folders for **'Output' and 'Templates'.**
3. **Save the extension** of the library name to be later used to update an environment variable. This will be in the format of: **/(library name)/Output**
4. From the **data folder in the repo**, download the **NDA template** (or an NDA template you plan to use) and upload this in the **'Templates' folder in the SharePoint library created in Step 1.2.1**.
5. Create a new [SharePoint document library](https://support.microsoft.com/en-us/office/create-a-document-library-in-sharepoint-306728fe-0325-4b28-b60d-f902e1d75939#ID0EBF=Modern) and name it as desired, for example, "SignedDocuments". This library will be used to store the signed NDA documents.
6. **Save the extension** of the library name to be later used to update an environment variable. This will be in the format of: **/SignedDocuments**

# Step 2: Docusign Setup

Docusign will be leveraged in this solution to capture the esignature of the customer the NDA contracts will be sent to.

## Step 2.1 Create Docusign account

1. If you don't have a Docusign account, please create a [free trial](https://www.docusign.com/) from the website.
2. If you do have an account with docusign, please have your credentials handy as they will be needed in Step 3.

## Step 2.2 Create Docusign custom fields

1. To access custom fields, log into Docusign as an administrator.
2. Navigate to My Preferences > Signing and Sending > Custom Fields.
3. Click **Add New Field.**
4. Create 2 custom fields **'AgreementID' and 'AgreementNumber'** both of type '**Text'**.
5. These 2 fields will be used to store the values of **Agreement ID and Agreement Number fields in Dataverse table** which will be leveraged to update the record with useful information.

# Step 3: Copilot Agent Setup

## Step 3.1 Import the Zip solution

1. The zip file in the solutions folder contains all the components needed for provisioning the AI agent.
2. Import the zip file in the [PowerApps Maker Portal](https://make.powerapps.com) in the power platform environment provisioned earlier.
3. During import, click '**sign in'** for any connections that prompt to do so. **You will need to provide credentials for Docusign from Step 2.1.2**
4. During import, **leave the 3 environment variables blank for now.**
5. After importing has completed, click **Publish all customizations**, and wait for publishing to complete.

## Step 3.2 Update Environment Variables

1. While being in the solution, go to the objects section from the left and click on **Environment variables**.
2. Update **Contract SharePoint Base URL** variable with the value from **Step 1.1.5**.
3. Update **Contract SharePoint Unsigned Folder Path** variable with the value from **Step 1.2.3**.
4. Update **Contract SharePoint Signed Folder Path** variable with the value from **Step 1.2.6**.
5. Click **Publish all customizations**, and wait for publishing to complete.

## Step 3.3 Update Power Automate flows

There are 7 power automate flows in this solution. Some of those will need to be updated as covered below. To see a list of all flows, navigate to **'Flows**' section in the [PowerApps Maker Portal](https://make.powerapps.com).

### Step 3.3.1 Populate a NDA Template flow

1. Open the NDA Template flow in **Edit mode** and click on the **'Populate a Microsoft Word Template'** action.
2. In the **Location**, choose your SharePoint site created in **Step 1.1**
3. In the **Document Library,** choose the 1st document library (like UnsignedDocumentsandTemplates) created in **Step 1.2.1**
4. In the **File**, choose the template from the 'Templates' folder that was uploaded in **Step 1.2.4**
5. **Save** the flow.

### Step 3.3.2 Docusign send for signature flow

1. Open the Docusign send for signature flow in **Edit mode** and click on the **'Get File content'** action.
2. Update the site address value to the SharePoint site created in **step 1.1.**
3. For all the subsequent Docusign actions, please make sure **Account** in all actions is selected to your account. This should be taken care of by default due to **step 3.1.3** but please check that to confirm.
4. **Save** the flow.

### Step 3.3.2 Docusign post signing flow

1. Open the Docusign post signing flow in **Edit mode.**
2. For all the Docusign actions, please make sure **Account** in all actions is selected to your account. This should be taken care of by default due to **step 3.1.3** but please check that to confirm.
3. In the **SharePoint Create File action,** select site address to be the SharePoint site from **Step 1.1** and **folder path** to be the document library created in **Step 1.2.5.**
4. In the SharePoint **Get File** Properties action, select site address to be the SharePoint site from **Step 1.1** and **library name** to be the document library created in **Step 1.2.5.**
5. **Save** the flow.

## Step 3.4 Sample data import

1. Dataverse tables are leveraged in this solution to track NDA agreement statuses, Account information and such. **Account sample data needs to be imported**.
2. In the [PowerApps Maker Portal](https://make.powerapps.com), go to Tables> Accounts > Import > Import Data
3. Select Excel workbook > Click Upload file in connection settings
4. Select Account Sample data file available from the Data folder of this repo.
5. Sign in if the connection needs to be refreshed.
6. Click Next
7. Click Sheet 1 > Next
8. On the transform section, select use first row as headers> Click Next
9. Load to an existing table > Select Account from the 'Destination table' dropdown.
10. Click Next> Publish

## Step 3.5 Publish Copilot Agent to Microsoft Teams

1. Go to [Copilot Studio Portal](https://copilotstudio.microsoft.com).
2. Please Publish your Copilot Agent by clicking '**Publish**'. This will make the copilot agent ready to be used. If there is a warning around no authentication that's expected per the use case.
3. Go to **Channels> Teams + Microsoft 365 > Add Channel.**
4. Please Publish your Copilot Agent by clicking '**Publish**'. This will make the copilot agent ready to be used in Teams.
5. Go to **Channels> Teams + Microsoft 365 >** **Availability Options > Copy Link**
6. Paste the link in a new window to access the agent in MS Teams.
