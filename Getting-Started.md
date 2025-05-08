# Getting Started with Your GitHub Advanced Security

### Overall Estimated Duration: 8 Hours

## Overview

In this hands-on lab, you’ll explore GitHub Advanced Security (GHAS) to enhance the security of your repositories. The lab includes using Dependabot and Software Composition Analysis (SCA) to identify and remediate dependency vulnerabilities.
You'll enable secret scanning with push protection, create custom secret patterns, and observe how active secrets are detected. You’ll also enable code scanning to detect security issues in your code and try out Copilot Autofix to automatically suggest secure code fixes. Finally, you'll scale GHAS adoption, review insights via the security dashboard, and integrate with external tools using webhooks.

## Objective

- **Dependency Scanning:** Enable dependency scanning to analyze project dependencies and identify known vulnerabilities in open-source libraries or third-party packages. This ensures your codebase remains secure by alerting you to outdated or vulnerable packages that need to be updated or replaced.

- **Secret Scanning:**: Implement secret scanning to automatically detect and alert on accidentally committed sensitive information such as API keys, passwords, or tokens. This helps prevent credential leaks and ensures sensitive data is never exposed in your repositories, reducing the risk of unauthorized access.

- **Code Scanning:**: Leverage advanced static code analysis to detect security vulnerabilities, coding errors, and potential exploits in your source code it helps to create a proactive approach towards security, reduce the potential impact of security threats, enhance the quality of code as well as speeding up the software development life cycle through minimizing time spent resolving post deployment issues.

- **Security Campaigns:** To help teams address security vulnerabilities at scale. These campaigns use Copilot Autofix to suggest fixes for up to 1,000 code scanning alerts at a time, allowing developers and security teams to collaborate efficiently. By prioritizing and fixing these alerts, teams can significantly reduce security debt and improve the overall security of their codebase

- **Azure Function App:** An Azure Function App is used to handle incoming events triggered by a GitHub webhook. When specific actions occur in a GitHub repository—such as pushes or pull requests—the webhook sends an HTTP request to the Function App. This enables automated processing, such as logging, validation, or integration with other services, making it a lightweight and scalable solution for responding to GitHub activity in real time.

## Pre-requisites

- Basic knowledge of GitHub
- Fundamental understanding of security principles, including vulnerability management and secure coding practices
- Familiarity with navigating and managing code repositories

## Architecture

In this hands-on lab, the architecture flow highlights key components of GitHub Advanced Security (GHAS) and its integration into the development workflow. It begins with an overview of GHAS and enabling essential security configurations at the organization level. The lab then explores core GHAS features, including Dependabot for dependency management, Secret Scanning for protecting sensitive information, and code scanning and vulnerability detection. Software Composition Analysis is used to assess open-source risks, while security campaigns drive consistent adoption across teams. The lab concludes with scaling GHAS implementation using a Function App, triggered via GitHub webhooks, to support automation and organization-wide security enforcement.

## Architecture Diagram

   ![](./images/arch15.png)

## Explanation of Components

1. **GitHub Secret Protection**, which includes features that help you detect and prevent secret leaks, such as secret scanning and push protection.

1. **GitHub Code Security**, which includes features that help you find and fix vulnerabilities, like code scanning, premium Dependabot features, and dependency review.

1. **Secret Scanning:** Detect secrets, for example keys and tokens, that have been checked into a repository and receive alerts.

2. **Code Scanning:** Search for potential security vulnerabilities and coding errors in your code using CodeQL or a third-party tool.

3. **Dependabot:** Dependabot is an automated dependency management tool that ensures a constant update of project dependencies. Dependabot keeps the development environment safe and steady by fixing bugs found in outdated dependencies.

1. **Copilot Autofix:** Get automatically generated fixes for code scanning alerts.

1. **Security campaigns:** Reduce security debt at scale.

1. **Function App:** It is a serverless compute service that enables you to run event-driven code without managing infrastructure. It automatically scales and executes functions in response to triggers like HTTP requests, timers, or webhooks.

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