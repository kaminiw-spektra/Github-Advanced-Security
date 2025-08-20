# Module 08: Scaling out GitHub Advanced Security (Optional)

### Estimated Duration: 60 Minutes

## Lab Scenario

In this module, you will focus on scaling GitHub Advanced Security (GHAS) adoption by aligning rollout strategies, leveraging the security overview dashboard for insights, integrating webhooks with external tools like SIEM, and implementing repository rulesets to enforce branch and tag policies—enhancing security and compliance across all repositories.

## Lab Objectives

In this module, you will perform:

- Task 1: How to grow adoption? How to communicate about GHAS internally?  
- Task 2: View the security overview dashboard and reports 
- Task 3: Review Webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
- Task 4: Talk about repository rulesets and how they can be used at scale 

## Architecture Diagram

   ![Picture1](../images/ar05.png) 

## Task 1: How to grow adoption? How to communicate about GHAS internally? [Read Only]

Adopting GitHub Advanced Security can be approached in multiple ways. It requires a strategic approach for success, especially in larger enterprises and organizations with thousands of repositories. This aims to lay the foundation for enterprises on how to adopt GHAS, but most importantly, scale it quickly and efficiently. Enabling GitHub Advanced Security across a large organization can be broken down into **six** core phases:

1. **Align your rollout strategy and goals**: Think about what success will look like, and align on how GHAS will be implemented in your company. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

1. **Preparing to enable at scale:** Prepare developers, collect data about your repositories, and ensure you're ready for the next phase.

1. **Pilot programs:** Optionally, pilot an initial rollout to a few high-impact projects and teams. This will allow an initial group within your company to get familiar with GHAS before you roll it out to the remainder of your company.

1. **Create internal documentation:** Create and communicate internal documentation for the GHAS consumers. Without proper documentation provided to developers, security engineers, and others who will be using GHAS. The value will get lost in the rollout.

1. **Rollout and scale code scanning:** Leverage the available APIs, automatically rollout code scanning by team and by language across your enterprise using the repository data you collected earlier.

1. **Rollout and scale secret scanning:** Roll out secret scanning, which involves less configuration and is therefore simpler to adopt than code scanning. Still, it's critical to have a strategy for handling new and old results.
   
**Phase One - Strategic Enablement Alignment**

Although it's appealing to rush into the implementation phase, take the time to align on how GHAS will be implemented in your enterprise. Additionally, think about what success could look like in the 3, 6, and 9 months after adoption. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

**Phase Two - Create Internal Documentation**

Like the above phase, organizations tend to rush into the implementation phase, as that stage is perceived to provide the quickest time-to-value. However, without the proper documentation and asynchronous resources provided to aid developers, security engineers, etc, in consuming GHAS correctly, the value gets lost in the rollout due to people not correctly consuming GHAS. Take the time to create internal documentation (such as training, how to remediate, where to go for questions, etc.), and then communicate this documentation (email, teams, slack, etc.) to the consumers of GHAS. So once you roll out GHAS, teams and people know what to do.

**Phase Three - Enable & Scale Code Scanning**

GHAS is an ecosystem of multiple solutions. It's essential to start somewhere focused, not just with the rollout of GHAS. Typically, teams focus on code scanning to begin with. Leverage the APIs available and rollout code scanning by the team and by language across your organization automatically. This allows you to scale in an automated fashion and removes a lot of manual repeatable groundwork for developers and consumers of code scanning. Doing this will increase adoption.

### Mean Time to Resolution

MTTR, or **Mean Time to Resolution**, is a metric used to measure the average time it takes to resolve issues, bugs, or incidents in a software project. In the context of GitHub, MTTR can be applied to various scenarios, such as:

Issue Resolution: MTTR can track the average time from when an issue is reported to when it is closed. This helps teams gauge their efficiency in addressing and fixing problems reported by users or detected during development.

   - **Pull Requests:** MTTR can measure the average time taken to review, approve, and merge pull requests. This helps teams understand how quickly they are integrating new code changes and handling contributions.

   - **Incident Response:** For repositories using GitHub Actions or other integrations, MTTR can track how long it takes to resolve incidents or failures reported by these tools.

## Task 2: View the security overview dashboard and reports [Read Only]

In this task, you will explore the GHAS security overview dashboard and reports to gain insights into your repository's security posture.

1. Go to your **profile icon** in the top right corner, and then select **Your organizations**.

   ![Picture1](../images/org.png) 
     
1. Select **ghas-bootcamp-xxxx-xx-xx-** from **organizations**.

   ![Picture1](../images/org-new1.png) 

1. Click the **Security** tab from the top right corner of the navigation bar.

   ![Picture1](../images/T2S3.png)

1. To explore the Security Overview dashboard, first click on **Overview (1)** in the left sidebar. At the top of the page, use the filter bar to narrow down alerts **(e.g., archived:false tool:github) (2)** and select a date range using the **calendar dropdown (3)**. As you adjust these filters, all data and metrics on the page, including graphs like **Open alerts over time**, will automatically update to reflect your selected criteria.

   ![Picture1](../images/dashboard1anew.png)
  
1. Click on the **Risk** option to view a comprehensive overview of all security risks across your repositories. This section provides detailed information about potential vulnerabilities, exposures, and other security concerns identified throughout your organization's repositories. It aggregates risk data, allowing you to assess and prioritize security issues at an organizational level, ensuring that you can address and mitigate risks effectively.

   ![Picture1](../images/mod1org8a.png)

1. Click on the **Coverage** option to access detailed information about the security coverage for your repositories. This section provides insights into the extent to which your code is being analyzed for vulnerabilities, including the number of lines of code covered by security scans and the effectiveness of your security measures. By reviewing the coverage data, you can ensure that your security scanning is comprehensive and identify areas where additional coverage may be needed.

   ![Picture1](../images/mod1org9a.png)
   
1. Analyze the metrics and data provided in the reports to identify areas for improvement and prioritize security efforts.

## Task 3: Review Webhooks and how they can be used to push events to an outside reporting tool, like an SIEM 

GitHub webhooks are a mechanism for automatically triggering actions or notifications in external systems when events occur within a GitHub repository. Users can configure webhooks to listen for specific events, such as pushes to a repository, pull request creation or closure, issue creation or comment, etc. When the specified event occurs, GitHub sends an HTTP POST payload to a designated URL, known as the payload URL, containing information about the event. This allows users to integrate GitHub with external services, such as CI/CD pipelines, issue trackers, or chat platforms. Thus enabling automated workflows and real-time notifications based on repository activities.

### Push events to an outside reporting function in the App.

In this task, you will configure GitHub webhooks to send push event data to an Azure Function, enabling automated event-driven integration with external reporting tools.

1. Open a **new InPrivate (Incognito) tab** in your browser and navigate to the Azure Portal at `https://portal.azure.com`.

   >**Note:** Please ensure you open a **new InPrivate (Incognito)** browser tab before logging into the Azure Portal to avoid session or credential conflicts.

2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
       ![Enter Your Username](../images/login1.png)
 
3. Next, provide your password to login:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![Enter Your Password](../images/login2.png)

1. On the **Stay signed in?** pop-up, click on **No**.

      > **Note**: If prompted with MFA, please follow the steps highlighted under - [Steps to Proceed with MFA Setup if Ask Later Option is Not Visible](#steps-to-proceed-with-mfa-setup-if-ask-later-option-is-not-visible), If you're already logged in to the Azure Portal, there's no need to perform this step — you can proceed to the next one.   

1. In the search bar of the Azure portal, type **Function app (1)**. From the search results, select **Function App (2)**.

   ![Picture1](../images/functionapp.png)

1. From the top-left corner of the Function App page, click **+ Create** to start creating a new Function App

   ![Picture1](../images/mod8-task3-step6new.png)

1. From the Create Function App tab, select **Consumption (1)** and click on **Select (2)**.

   ![Picture1](../images/ghas-exercise1-9a.png)

1. On the **Basics** tab of Create Function App, provide details as mentioned in the table below and select **Review + create (8)** at the bottom of the page and subsequently click on **Create (9)**.

    | Setting | Action |
    | -- | -- |
    | **Subscription** | Keep it as default **(1)** |
    | **Resource Group** | Lab-VM **(2)** |
    | **Function App name** | **function-webhooks-<inject key="DeploymentID" enableCopy="false"/> (3)** |
    | **Operating System** | **Windows (4)** |    
    | **Runtime stack** | **Node.js (5)** |
    | **Version** | **20 LTS (6)** |
    | **Region** | **East US (7)** |

   ![Picture1](../images/T3S8.png)

   ![Picture1](../images/mod8-task3-step8new1.png)

     >**Note:** Keep rest of the options as default.

     >**Note:** If you encounter any issues related to the region, you can try using a different region, such as **Canada Central, East US 2**, etc.
 
1. Once the deployment is completed, click on **Go to resource**.

   ![Picture1](../images/functionapp3a.png)

1. On the **Overview (1)** page of the **Function app**, under the  **Functions** tab, click on **Create function (2)**. It will open a  page for **Create function**. Search for and select **HTTP trigger (3)**. Click on **Next (4)**.

   ![Picture1](../images/functionapp3.png)

1. On Template details page, leave the default options and click on **Create**.

   ![Picture1](../images/T3S10new1.png)

   > **Note :** If you get any **error message**, **refresh** the page and the function which you created will be present under the functions tab in the overview page.

1. Under the **Function** tab, you can see the created Function. Click on it.

    ![Picture1](../images/fuctionabc.png)

1. From the top menu of your Function App, click on the **Invocations tab** to view recent function execution traces.

    ![Picture1](../images/T3S13.png)

   > **Note:** If you see the option **"Configure Application Insights to capture invocation logs"**, follow the steps below. If not, proceed to **Step 14**.

     ![Picture1](../images/functionabf.png)

   1. Click on **Configure** to enable invocation log capture.

   2. Select **Turn on Application Insights**.

      ![Picture1](../images/functionabe.png)

   3. Scroll down and choose the existing **Log Analytics Workspace**.

      ![Picture1](../images/functionabg.png)

   4. Click **Apply (1)**, then confirm by clicking **Yes (2)** to apply the monitoring settings.

      ![Picture1](../images/functionabhnew.png)

   5. Wait for the configuration to complete. Then, go back to your **HttpTrigger1** function and open the **Invocations** tab — you should now see it is configured.

      ![Picture1](../images/functionabd.png)

1. To get the function URL for your Azure HTTP-triggered function, first go to the **Code + Test (1)** tab, then click on **Get function URL (2)**. Copy the **default (Function key) (3)** URL from **copy (4)** icon.
   
    ![Picture1](../images/trigger1new.png)

1. Navigate to the **setting** tab of your **GitHub Organization**..

   ![Repository Settings](../images/T3S15.png)

1. Click on **Webhooks** from the left Navigation pane.

   ![Picture1](../images/T3S16.png)

1. Click on **Add webhook** and give your GitHub password.

   ![Picture1](../images/mod8-task3-step17new.png)

1. In the GitHub repository, navigate to the **Webhooks** settings. Paste the URL generated by the HttpTrigger function into the **Payload URL (1)** field. This URL will be used to send requests to your Azure Function whenever events occur in the repository.

   - **Content type**: Select **application/json (2)** so that you can receive the payload as a JSON object.
   - **Secret**: You can leave this blank.
   - **SSL verification**: Leave this as the default option of **Enable SSL verification (3)**.
   - **Which events would you like to trigger this webhook?** Select the **Just the push event (4)** option.
   - **Active (5)**: Leave this checked to receive event details when the GitHub Webhook is triggered.
   - Click on **Add webhook (6)**.

      ![Picture1](../images/T3S18.png)

      >**Note**: You can also select **"Send me everything"** or **"Let me select individual events"** for your webhook instead of **just the push event**. This approach allows you to gain a deeper understanding and experiment with different types of events.

11. From the top menu, click on **Repositories (1)** in the left pane, then click on the **New repository (2)** button on the right side to create a new repository.

    ![Picture1](../images/T3S19new.png)

12. To create the repository, name it **Test-webhook (1)**, select **Internal (2)** as the visibility option, ensure to check **Add a README file (3)** to initialize the repository, and finally, click on **Create repository (4)** to complete the process.

    ![Picture1](../images/T3S20.png)
  
    >**Note**: You can make some more changes to your repositories. It will send the PUSH request to the function app.

13. From the repository page, click on **Add file (1)** (or the **+ icon**) in the top right, then select **Create new file (2)** from the dropdown.

     ![Picture1](../images/T3S21.png)

14. Create a file named **issue-template.md** **(1)**, add the provided code into the file **(2)**, and then click on **Commit changes...** **(3)** to save.

    ```
    ## Build Failure

    **Workflow:** ${{ github.workflow }}  
    **Branch:** ${{ github.ref }}  
    **Commit:** ${{ github.sha }}  
    **Actor:** ${{ github.actor }}  

    ### Logs
    See the attached logs for more details.
    ```

     ![Picture1](../images/T3S22.png)

15. Enter the commit message and click **Commit changes** to save.

     ![Picture1](../images/lab7testwebhook3.png)

16. Navigate to the **Actions** tab to view and manage your GitHub Actions workflows.

     ![Picture1](../images/T3S24.png)

17. On the **Get Started with GitHub Actions** page, click on the **Configure** button for **Simple workflow** to begin setting up a workflow.

     ![Picture1](../images/lab7testwebhook5.png)

18. Change the file name of the YAML configuration file to **ci.yml** **(1)**. Paste the provided **code** **(2)** into this file to define the workflow configuration. Finally, click on **Commit changes...** **(3)** to save the file with these updates.

	```
	name: CI 
	
	on: [push, pull_request] 
	
	jobs: 
	  build: 
	    runs-on: ubuntu-latest 
	
	    steps: 
	      - name: Check out the repository 
	        uses: actions/checkout@v2 
	
	      - name: Set up Python 
	        uses: actions/setup-python@v2 
	        with: 
	          python-version: '3.x' 
	
	      - name: Install dependencies 
	        run: | 
	          python -m pip install --upgrade pip 
	          pip install -r requirements.txt 
	
	      - name: Run tests 
	        id: run-tests 
	        run: | 
	          pytest --junitxml=test-results.xml 
	        continue-on-error: true 
	
	      - name: Upload Test Results 
	        if: always() 
	        uses: actions/upload-artifact@v2 
	        with: 
	          name: test-results 
	          path: test-results.xml 
	
	      - name: Create GitHub Issue on Failure 
	        if: failure() 
	        uses: actions/create-issue@v2 
	        with: 
	          token: ${{ secrets.GITHUB_TOKEN }} 
	          title: Build Failure 
	          body-path: ./issue-template.md 
	          labels: bug 
	          assignees: your-github-username 
	 
	```

     ![Picture1](../images/T3S26.png)

19. Enter the commit message and click **Commit changes** to save.

     ![Picture1](../images/lab7testwebhook7.png)

20. Navigate to the **Actions (1)** tab, where you'll find that the creation of **ci.yml** **(2)** failed due to an issue.

     ![Picture1](../images/lab7testwebhook8.png)

13. Navigate back to **your organization**, and click on **Settings**.

     ![Repository Settings](../images/T3S15.png)

14. From the left navigation pane, click on **Webhooks**.

      ![](../images/mod8-task3-step30new.png)

1. Select the Webhook you have created.

    ![Picture1](../images/recentdeliverya.png)

15. Scroll down to the bottom and you will find some **Recent Deliveries**.

    ![Picture1](../images/recentdelivery.png)

16.  Click on any deliveries. You will see their **Request** and **Response** column for more information.

     ![Picture1](../images/request.png)

     ![Picture1](../images/response.png)

17. Navigate back to your **Function app** in the Azure portal and select the HTTP trigger function you created. Click on **Invocations**. This section provides the most recent invocation traces, allowing you to review and analyze the function's execution history.

    ![Picture1](../images/mod8-task3-step34new.png)
   
    >**Note:** It will take 5-7 minutes to show.

## Task 4: Talk about repository rulesets and how they can be used at scale [Read Only]

1. A ruleset is a named list of rules that applies to a repository. You can create rulesets to control how people interact with selected branches and tags in a repository. You can also control things like who can push commits to a certain branch or who can delete or rename a tag. For example, you could set up a ruleset for your repository's feature branch that requires signed commits and blocks force pushes for all users except repository administrators.

1. For each ruleset you create, you specify which branches or tags in your repository the ruleset applies to. You can use the **fnmatch syntax** to define a pattern and target specific branches and tags. For example, you could use the pattern releases/**/* to target all branches in your repository whose name starts with the string releases/.

1. When you create a ruleset, you can allow certain users to bypass the rules. This can be users with a certain role, such as repository administrator, or it can be specific teams or GitHub apps.

1. There is a limit of 75 rulesets per repository.

### Creating rulesets for a repository

You can create rulesets to control how users interact with selected branches and tags in a repository. When you create a ruleset, you can allow certain users to bypass the rules. This can be users with certain permissions, specific teams, or GitHub apps.

1. Create a **branch** or tag **ruleset**.

1. On GitHub, navigate to the **main page** of the repository.

1. Under any of	 your repository name, click on **Settings**. If you cannot see the "Settings" tab, select the **...**  dropdown menu, then click on **Settings**.

   ![Picture1](../images/ghasr1.png)  

1. In the left sidebar, under **Code and automation (1)** click **Rules (2)** and then click on **Rulesets (3)**.

   ![Picture1](../images/T4S4.png)    

1. You can create a ruleset targeting branches, or a ruleset targeting tags.

   - To create a ruleset targeting branches, click on **New branch ruleset**.
   - To create a ruleset targeting tags, select **New tag ruleset**.

      ![Picture1](../images/mod8-task4-step5new.png)  
  
1. In the **New branch ruleset** section, type a name for the **ruleset (1)**, then select **Disabled (2)**  and click one of the following enforcement statuses:

   - **Active**: Your ruleset will be enforced upon creation.
   - **Disabled**: Your ruleset will not be enforced.

      ![](../images/rulesetnew.png) 

In summary, repository rulesets enhance security, compliance, and consistency across repositories, especially when managing large-scale projects. 

For more details, refer to the [GitHub documentation on rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)

## Steps to Proceed with MFA Setup if Ask Later Option is Not Visible

   > **Note:** These are the steps to enable MFA if it is enforced during login to the Azure portal. If you've already logged in successfully, you can skip this step. Otherwise, enable MFA and then continue from where you left off. 

1. At the **"More information required"** prompt, select **Next**.

1. On the **"Keep your account secure"** page, select **Next** twice.

1. **Note:** If you don’t have the Microsoft Authenticator app installed on your mobile device:

   - Open **Google Play Store** (Android) or **App Store** (iOS).
   - Search for **Microsoft Authenticator** and tap **Install**.
   - Open the **Microsoft Authenticator** app, select **Add account**, then choose **Work or school account**.

1. A **QR code** will be displayed on your computer screen.

1. In the Authenticator app, select **Scan a QR code** and scan the code displayed on your screen.

1. After scanning, click **Next** to proceed.

1. On your phone, enter the number shown on your computer screen in the Authenticator app and select **Next**.
       
1. If prompted to stay signed in, you can click **No**.

1. If a **Welcome to Microsoft Azure** popup window appears, click **Cancel** to skip the tour.
 
1. Now, click on the **Next** from the lower right corner to move to the next page.


## Summary

In this module, you have completed the following:

+ How to grow adoption? How to communicate about GHAS internally?  
+ Viewed the security overview dashboard and reports 
+ Reviewed Webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
+ Talked about repository rulesets and how they can be used at scale 

## You have successfully completed this Hands-on lab.

By completing this hands-on lab on **Securing Repositories with GitHub Advanced Security**, you gained practical experience in implementing and managing GHAS features across repositories and organizations. You explored core components like code scanning, secret scanning, Dependabot, and dependency review, while also configuring organization-wide security settings, Copilot Autofix, push protection, and security dashboards. Additionally, you learned how to scale security using repository rulesets and integrate with external tools. These skills are essential for securing software projects in academic, enterprise, and open-source environments.



