# Agent for Contract Processing

This solution streamlines contract management by creating, finding, managing and sharing contracts which lead to saving time and resources by automating contract processing workflows. The solution leverages Copilot Studio, Dataverse, Power Automate, SharePoint, Microsoft Teams and a 3rd party e-signature connector.

<br/>

<div align="center">
  
[**SOLUTION OVERVIEW**](#solution-overview)  \| [**QUICK DEPLOY**](#quick-deploy)  \| [**BUSINESS USE CASE**](#business-use-case)  \| [**SUPPORTING DOCUMENTATION**](#supporting-documentation)

</div>
<br/>

<h2><img src="./Deployment/Images/solution-overview.png" width="48" />
Solution overview
</h2>

The Agent for Contract Processing helps employees quickly create, find, manage and share contracts, saving time and resources by automating contract processing workflows. 

Leveraging Copilot Studio, Power Platform, Microsoft Teams, SharePoint and 3rd party e-signature tools, employees can generate, search and summarize contracts, automate e-sign processes with customers and converse naturally with the agent.

**Note:** This accelerator is not intended to be a production ready solution. The components can be extended through customization and configuration as desired to create a production ready solution. All components packaged have been done through an unmanaged solution, which allows users to be able to customize and extend the components post-deployment.

### Solution architecture

![Architecture](./Deployment/Images/architecture.png)

### How to customize
This solution is designed to be easily customizable. All configuration and customizations to this solution will be done in Power Platform and Copilot Studio.

**A note on extension opportunities with Conversation Start Adaptive Card**

Note that in the initial Adaptive Card that presents three options (Check if a customer has an NDA; Get information about an NDA; Create a new NDA), the first two options both currently initiate a search for existing NDAs in place for a given organization. As an extension, you may choose to include additional functionality for the second of these options, to provide additional summarization information about the agreement, beyond what is included in the Adaptive Card summary.

**Additional opportunities for extension**

There are a variety of opportunities to extend the functionality of this accelerator. Some of these include:

 * Including an in-house legal team eSignature signing step, rather than using a pre-signed template
 * Catering for customer-specific clauses in the agreement
 * Including an internal approval step, potentially using the [Approvals Connector](https://learn.microsoft.com/en-us/connectors/approvals/)
 * Integration with 3rd-party contract management systems
 * Using Generative AI to summarize agreement content, or compare content between a standard vs proposed agreement
 * and more

### Additional resources

This accelerator focuses on harnessing the following key capabilities:

* [User intent detection in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/cux-identify-intents)
* [Adaptive Cards in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/adaptive-cards-overview)
* [Publishing Copilot agent in Microsoft Teams](https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams)
* [Capturing e-signatures using DocuSign](https://learn.microsoft.com/en-us/connectors/docusign/)
* [Configure tables in Dataverse](https://learn.microsoft.com/en-us/training/modules/get-started-with-powerapps-common-data-service/)
* [Using SharePoint library for document storage](https://support.microsoft.com/en-us/office/create-a-document-library-in-sharepoint-306728fe-0325-4b28-b60d-f902e1d75939)

Additional details on how these capabilities are leveraged in this accelerator can be found here:

* [Dynamically-generated Adaptive Cards in Topics](./Deployment/Differentiators/DIFFERENTIATORS.md#adaptive_cards)
* [Use of entities and slot filling](./Deployment/Differentiators/DIFFERENTIATORS.md#slot_filling)
* [Modular topics with inputs and outputs](./Deployment/Differentiators/DIFFERENTIATORS.md#modular_topics)
* [Document manipulation](./Deployment/Differentiators/DIFFERENTIATORS.md#document_manipulation)
* [E-signature connector usage](./Deployment/Differentiators/DIFFERENTIATORS.md#esignature)

<br/>

### Key features
<details open>
  <summary>Click to learn more about the key features this solution enables</summary>

  - **Generate contracts** <br/>
  Draft contracts from templates and existing knowledge base to outline right terms and conditions to never start from scratch.​
  
  - **Search and summarize** <br/>
  Find existing contracts, extract entries and clauses through records and review contracts to save time.

  - **Automate processes** <br/>
  Automate routine tasks such as review and approval, obtaining signatures, as well as enable seamless collaboration across organization.

  - **Extend and integrate** <br/>
  Enhance user experience by enabling integration and extensibility with relevant third-party corporate systems such as DocuSign.​

  - **Converse naturally** <br/>
  Enhance communication and interaction through AI-driven chat, Q&A, and contextual responses within system of productivity such as Teams.
       
</details>

<br /><br />
<h2><img src="./Deployment/Images/quick-deploy.png" width="48" />
Quick deploy
</h2>

### How to install or deploy
Please click this [**Link to Deployment Guide**](Deployment/README.md) for instructions on how to deploy and set up the solution accelerator.

[**Usage Guidance**](Deployment/Data/USAGE_GUIDANCE.md) has been provided to assist you in executing the steps required to see the included capabilities of this accelerator in action..

{🟨TODO: Fill in table with deployment specific links}

| [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/microsoft/content-processing-solution-accelerator) | [![Open in Dev Containers](https://img.shields.io/static/v1?style=for-the-badge&label=Dev%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/microsoft/content-processing-solution-accelerator) | 
|---|---|

<br/>

{🟨TODO: Remove if Azure OpenAI quota check is not required }

> ⚠️ **Important: Check Azure OpenAI Quota Availability - do not have content**
 <br/>To ensure sufficient quota is available in your subscription, please follow [quota check instructions guide](./docs/QuotaCheck.md) before you deploy the solution.

<br/>

### Prerequisites and Costs - do not have content
{🟨TODO: Update with solution specific notes like role requirements}

To deploy this solution accelerator, ensure you have access to an [Azure subscription](https://azure.microsoft.com/free/) with the necessary permissions to create **resource groups, resources, app registrations, and assign roles at the resource group level**. This should include Contributor role at the subscription level and  Role Based Access Control role on the subscription and/or resource group level. Follow the steps in [Azure Account Set Up](./docs/AzureAccountSetUp.md).

Here are some example regions where the services are available: {🟨TODO: Update with suggested regions specific to this solution}

Check the [Azure Products by Region](https://azure.microsoft.com/en-us/explore/global-infrastructure/products-by-region/?products=all&regions=all) page and select a **region** where the following services are available.

{🟨TODO: Call out specific pricing "gotchas" like Azure Container Registry if known}

Pricing varies per region and usage, so it isn't possible to predict exact costs for your usage. The majority of the Azure resources used in this infrastructure are on usage-based pricing tiers. However, Azure Container Registry has a fixed cost per registry per day.

{🟨TODO: Update with solution specific estimate sheet}

Use the [Azure pricing calculator](https://azure.microsoft.com/en-us/pricing/calculator) to calculate the cost of this solution in your subscription. 

Review a [sample pricing sheet](https://azure.com/e/68b51f4cb79a4466b631a11aa57e9c16) in the event you want to customize and scale usage.

_Note: This is not meant to outline all costs as selected SKUs, scaled use, customizations, and integrations into your own tenant can affect the total consumption of this sample solution. The sample pricing sheet is meant to give you a starting point to customize the estimate for your specific needs._

<br/>

{🟨TODO: Update with all products, decription of product use, and product specific pricing links}

| Product | Description | Cost |
|---|---|---|
| [Product Name with Link to Learn content](https://learn.microsoft.com) | Decription of how the product is used | [Pricing]() |
| [Product Name with Link to Learn content](https://learn.microsoft.com) | Decription of how the product is used | [Pricing]() |
| [Product Name with Link to Learn content](https://learn.microsoft.com) | Decription of how the product is used | [Pricing]() |
| [Product Name with Link to Learn content](https://learn.microsoft.com) | Decription of how the product is used | [Pricing]() |


<br/>

>⚠️ **Important:** To avoid unnecessary costs, remember to take down your app if it's no longer in use,
either by deleting the resource group in the Portal or running `azd down`.

<br /><br />
<h2><img src="./Deployment/Images/business-scenario.png" width="48" />
Business Use Case
</h2>

Below is a sample landing page of the solution accelerator after it is deployed, set up, and ready to be used:
![Key Features](./Deployment/Images/landingpage.png)

An employee wants to initiate a request for contract creation (a Non-disclosure Agreement with a customer, or NDA in this example) to allow them to proceed with their sales opportunity with a second party organization. The employee chats with the Agent for Contract Processing in Teams, which helps the employee confirm whether or not an NDA contract already exists for the customer. If not, the agent initiates the contract creation by requesting all required information from the employee. Once the information is provided, the agent automatically creates a draft version of the contract and presents it to the employee to confirm if it's ready to be sent to the customer for eSignature. Once the employee reviews the draft and is satisfied, the agent sends the contract to the customer for the eSignature. Once the eSignature process is completed, the signed document is stored in SharePoint, and a Dataverse record is created which stores the status, SharePoint URL, agreement ID and other important details of the NDA Agreement.

By being able to get an executed NDA agreement in place quickly and seamlessly, and without involving in-house legal resources, the employee is able to proceed with their sales opportunity quickly, and the employee's legal department is able to focus on higher-value legal scenarios rather than repetitive tasks.

### Business value
<details>
  <summary>Click to learn more about what value this solution provides</summary>

  - **​Increased efficiency and time savings** <br/>
  Reduced time spent on manual legal tasks, allowing teams to focus on high-value work. Faster contract processing and compliance checks lead to improved productivity across legal operations.

  - **Faster content analysis** <br/>
  AI-powered tools automate contract search and review, reducing delays and improving oversight helping legal teams make faster, data-driven decisions with improved contract visibility.

  - **Optimized contract management** <br/>
  Integrated systems connect legal tools with contract management platforms to eliminate workflow bottlenecks, reduce administrative workload, and accelerate approvals.

  - **Improved collaboration** <br/>
  Effective coordination between legal teams, business stakeholders, and external counsel ensures smoother contract creation, edits, and approvals, improving overall legal outcomes.
     
</details>

<br /><br />

<h2><img src="./Deployment/Images/supporting-documentation.png" width="48" />
Supporting documentation
</h2>

1. [Microsoft Power Platform](https://learn.microsoft.com/en-us/power-platform/)
2. [Microsoft Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/)

### Security guidelines - do not have content

{🟨TODO: Fill in with solution specific security guidelines similar to the below}

This template uses Azure Key Vault to store all connections to communicate between resources.

This template also uses [Managed Identity](https://learn.microsoft.com/entra/identity/managed-identities-azure-resources/overview) for local development and deployment.

To ensure continued best practices in your own repository, we recommend that anyone creating solutions based on our templates ensure that the [Github secret scanning](https://docs.github.com/code-security/secret-scanning/about-secret-scanning) setting is enabled.

You may want to consider additional security measures, such as:

* Enabling Microsoft Defender for Cloud to [secure your Azure resources](https://learn.microsoft.com/azure/security-center/defender-for-cloud).
* Protecting the Azure Container Apps instance with a [firewall](https://learn.microsoft.com/azure/container-apps/waf-app-gateway) and/or [Virtual Network](https://learn.microsoft.com/azure/container-apps/networking?tabs=workload-profiles-env%2Cazure-cli).

<br/>

### Frequently asked questions - do not have content

{🟨TODO: Remove this section if you don't have FAQs}

[Click here](./docs/FAQs.md) to learn more about common questions about this solution.

<br/>

### Cross references - do not have content
Check out similar solution accelerators
 
{🟨TODO: Identify related accelerators - fill in the name and a one sentence description. The name should have non-breaking spaces in them to make sure the layout doesn't break.}

| Solution Accelerator | Description |
|---|---|
| [Document&nbsp;knowledge&nbsp;mining](https://github.com/microsoft/Document-Knowledge-Mining-Solution-Accelerator) | Provides REST API access to OpenAI's powerful language models including o3-mini, o1, o1-mini, GPT-4o, GPT-4o mini |
| [Conversation&nbsp;knowledge&nbsp;mining](https://github.com/microsoft/Conversation-Knowledge-Mining-Solution-Accelerator) | Description of solution accelerator |
| [Document&nbsp;generation](https://github.com/microsoft/document-generation-solution-accelerator) | Analyzes various media content—such as audio, video, text, and images—transforming it into structured, searchable data |


<br/>   


## Provide feedback - do not have content

{🟨TODO: Update link to create new issues for this repo}

Have questions, find a bug, or want to request a feature? [Submit a new issue](https://github.com/microsoft/content-processing-solution-acclerator/issues) on this repo and we'll connect.

<br/>

## Responsible AI Transparency FAQ - do not have content
Please refer to [Transparency FAQ](./TRANSPARENCY_FAQ.md) for responsible AI transparency details of this solution accelerator.

<br/>

# Disclaimers

This release only supports English language input and output. Users should not attempt to use the system with any other language or format. The system output may not be compatible with any translation tools or services, and may lose its meaning or coherence if translated.

This release does not reflect the opinions, views, or values of Microsoft Corporation or any of its affiliates, subsidiaries, or partners. The system output is solely based on the system's own logic and algorithms, and does not represent any endorsement, recommendation, or advice from Microsoft or any other entity. Microsoft disclaims any liability or responsibility for any damages, losses, or harms arising from the use of this release or its output by any user or third party.

This release is intended as a proof of concept only, and is not a finished or polished product. It is not intended for commercial use or distribution, and is subject to change or discontinuation without notice. Any planned deployment of this release or its output should include comprehensive testing and evaluation to ensure it is fit for purpose and meets the user's requirements and expectations. Microsoft does not guarantee the quality, performance, reliability, or availability of this release or its output, and does not provide any warranty or support for it.

This Software requires the use of third-party components which are governed by separate proprietary or open-source licenses as identified below, and you must comply with the terms of each applicable license in order to use the Software. You acknowledge and agree that this license does not grant you a license or other right to use any such third-party proprietary or open-source components.

To the extent that the Software includes components or code used in or derived from Microsoft products or services, including without limitation Microsoft Azure Services (collectively, “Microsoft Products and Services”), you must also comply with the Product Terms applicable to such Microsoft Products and Services. You acknowledge and agree that the license governing the Software does not grant you a license or other right to use Microsoft Products and Services. Nothing in the license or this ReadMe file will serve to supersede, amend, terminate or modify any terms in the Product Terms for any Microsoft Products and Services.

You must also comply with all domestic and international export laws and regulations that apply to the Software, which include restrictions on destinations, end users, and end use. For further information on export restrictions, visit [https://aka.ms/exporting](https://aka.ms/exporting).

You acknowledge that the Software and Microsoft Products and Services (1) are not designed, intended or made available as a medical device(s), and (2) are not designed or intended to be a substitute for professional medical advice, diagnosis, treatment, or judgment and should not be used to replace or as a substitute for professional medical advice, diagnosis, treatment, or judgment. Customer is solely responsible for displaying and/or obtaining appropriate consents, warnings, disclaimers, and acknowledgements to end users of Customer’s implementation of the Online Services.

You acknowledge the Software is not subject to SOC 1 and SOC 2 compliance audits. No Microsoft technology, nor any of its component technologies, including the Software, is intended or made available as a substitute for the professional advice, opinion, or judgement of a certified financial services professional. Do not use the Software to replace, substitute, or provide professional financial advice or judgment.

BY ACCESSING OR USING THE SOFTWARE, YOU ACKNOWLEDGE THAT THE SOFTWARE IS NOT DESIGNED OR INTENDED TO SUPPORT ANY USE IN WHICH A SERVICE INTERRUPTION, DEFECT, ERROR, OR OTHER FAILURE OF THE SOFTWARE COULD RESULT IN THE DEATH OR SERIOUS BODILY INJURY OF ANY PERSON OR IN PHYSICAL OR ENVIRONMENTAL DAMAGE (COLLECTIVELY, “HIGH-RISK USE”), AND THAT YOU WILL ENSURE THAT, IN THE EVENT OF ANY INTERRUPTION, DEFECT, ERROR, OR OTHER FAILURE OF THE SOFTWARE, THE SAFETY OF PEOPLE, PROPERTY, AND THE ENVIRONMENT ARE NOT REDUCED BELOW A LEVEL THAT IS REASONABLY, APPROPRIATE, AND LEGAL, WHETHER IN GENERAL OR IN A SPECIFIC INDUSTRY. BY ACCESSING THE SOFTWARE, YOU FURTHER ACKNOWLEDGE THAT YOUR HIGH-RISK USE OF THE SOFTWARE IS AT YOUR OWN RISK.