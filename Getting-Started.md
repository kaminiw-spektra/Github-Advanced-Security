# Getting Started with Your GitHub Advanced Security

### Overall Estimated Duration: 8 Hours

## Overview

In this hands-on lab, you’ll explore GitHub Advanced Security (GHAS) to enhance the security of your repositories. The lab includes using Dependabot and Software Composition Analysis (SCA) to identify and remediate dependency vulnerabilities.
You'll enable secret scanning with push protection, create custom secret patterns, and observe how active secrets are detected. You’ll also enable code scanning to detect security issues in your code and try out Copilot Autofix to automatically suggest secure code fixes. Finally, you'll scale GHAS adoption, review insights via the security dashboard, and integrate with external tools using webhooks.

## Objective

By the end of this lab, you will be able to:

- **Use your own data with Azure OpenAI**: This hands-on exercise aims to provision an Azure OpenAI resource and deploy a model, observing its normal chat behavior initially. You will then connect your data, interact with the model using this data, set up and configure an application in Cloud Shell, and run it to test its functionality.
- **Explore content filters in Azure OpenAI**: This hands-on exercise aims to deploy an OpenAI model to generate natural language output and explore content filters to ensure the generated content meets desired standards. The content filtering system recognizes and responds to particular types of potentially dangerous content in input prompts and output completions.
  
## Pre-requisites

- Basic knowledge of GitHub
- Fundamental understanding of security principles, including vulnerability management and secure coding practices
- Familiarity with navigating and managing code repositories

## Architecture

The architecture flow involves using the Azure OpenAI Service to integrate your data with a large language model (LLM), allowing you to manage how the model interacts with your information by focusing on specific topics or blending it with pre-trained results. The service employs default content filters to detect and remove harmful content, and you can also apply custom filters tailored to your needs. This approach ensures that content filtering is effectively used to uphold responsible AI practices, providing insights into its role in maintaining secure and safe interactions.

## Architecture Diagram

  ![](../media/arch15.PNG)

## Explanation of Components

1. **Azure OpenAI**: Azure OpenAI Service provides REST API access to OpenAI's powerful language models and these models integrates with your data, enabling customized and secure interactions.
1. **Azure OpenAI Models**: Offers pre-trained and customizable large language models for various AI applications. These models allow for powerful AI-driven solutions by generating tailored and contextually relevant content based on well-crafted prompts.
1. **Azure CloudShell**: Azure CloudShell offers an integrated, browser-based shell experience for managing Azure resources. It provides a ready-to-use environment with pre-installed tools and access to both Bash and PowerShell.
1. **Storage Account**: Manages and stores data, providing scalable and secure cloud storage solutions.
1. **Content Filter**: Detects and removes harmful content to ensure safe and responsible AI interactions.

## Getting Started with the Lab
## Accessing Your Lab
 
Once you're ready to begin, you’ll find the **Lab Guide**, which you will use throughout the lab.

   ![Picture1](./images/guide.png)

## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab. Here, you will find the Azure and GitHub credentials. Click on the **GitHub Credentials** option to access the GitHub user credentials.

   ![Picture1](./images/2nda.png)

## Lab Guide Zoom In/Zoom Out
 
To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![](./images/zoom-feature.png)

## Login to GitHub

1. On your **computer or desktop**, search for any browser and open it. You can use any browser of your choice.

1. Copy the link and open it in a browser window to log in to GitHub 

   > **Note:** Open the link in a **New Private Window** and use only the provided GitHub credentials. Do not use your personal GitHub account.

   ```
   https://github.com/login
   ```

2. In the sign-in to GitHub page in the Edge browser, enter the **GitHub UserEmail** and **GitHub Password** and click on **Sign in**.

   ![Picture1](./images/github.png)

   >**Note:** Make sure to use the **GitHub credentials** allotted to you from the environment details page of your lab.
   
   >**Note:** Navigate to the **Environment** tab to view the key-value pairs of the **GitHub Org User**, and **GitHub Org Password**. You can use the copy buttons under the actions column to have the values copied instantly. Alternatively, it is suggested to have the values copied over onto a notepad for easy accessibility. 

    ![Picture1](./images/2nda.png)

1. Next, to get the authentication code, sign in to Outlook through opening a new tab with the **GitHub** credentials that were copied over to Notepad in the previous step. After logging into Outlook, locate the most recent email that contains the verification code, and then select **Verify** to return to the login screen.

   ```
   https://outlook.office365.com/mail/
   ```

   >**Note:** Make sure to log in to Outlook using the **GitHub credentials** provided to you from the environment details page of your lab.

   >**Note:** The email containing the verification code can sometimes creep into the archive/spam folders within your Outlook.
   
   ![Picture1](./images/verify1.png)

   >**Note:** Please do not enable Two-Factor Authentication (2FA) after logging into GitHub for this lab. To avoid complications, use GitHub user accounts as outlined in the lab instructions. This will help prevent any issues related to 2FA validation during the exercise.

1. Accept the GitHub invitation using the same Outlook account.

    ![Picture1](./images/invitation.png)

1. Click the invitation link to join, once it opens in Github.

    ![Picture1](./images/invitation1.png)

1. Click "Next" from the bottom right corner to embark on your Lab journey!

   ![Picture1](./images/Sec1.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on Next from the lower right corner to move on to the next page.

## Happy Learning!!