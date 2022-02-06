# Snyk Code and Snyk Open Source Workshop

Snyk Code and Snyk Open Source together provide easy-to-use, fast and accurate SAST and SCA testing, enabling developers and security teams to easily find and fix both security issues in their own proprietary code as well as known vulnerabilities in their open source dependencies, reducing risk and improving the pace of development

## Prerequisites

* public GitHub account - http://github.com
* git CLI - https://git-scm.com/downloads
* snyk CLI - https://support.snyk.io/hc/en-us/articles/360003812538-Install-the-Snyk-CLI
* Registered account on Snyk App - http://app.snyk.io

## What we will do in this hands-on workshop?

In this hands-on workshop we will achieve the following:

* [Step 1 - Fork the highly vulnerable Juice-Shop Application]()
* [Step 2 - Configure GitHub Integration]()

Snyk Code steps

* [Step 3 Enable Snyk Code within Snyk App]()
* [Step 4 Add project to find Snyk Code Vulnerabilities]()
* [Step 5 Run a Snyk Code CLI Test]()

Snyk Open Source steps

* [Step 6 Find vulnerabilities]()
* [Step 7 Fix using a Pull Request]()
* [Step 8 Run a Snyk CLI Test]()

# Workshop Steps

_Note: It is assumed your using a mac for these steps, but it should also work on Windows or linux with some modifications to the scripts potentially_

<br />

## Step 1 - Fork the highly vulnerable Juice-Shop Application

_NOTE: You may have already forked the Juice-Shop application in that case go ahead and skip this step_

Navigate to the following GitHub repo - https://github.com/JennySnyk/juice-shop

_NOTE: this repo comes from the project Juice Shop from OWASP_

* Click on the "**Fork**" button
* Ensure you are forking this repo to your public GitHub account
* Click done

![alt tag](https://i.ibb.co/PYCX43Q/Juice-Shop-Github.png)

## Step 2 - Configure GitHub Integration

_NOTE: You may have already setup GitHub integration in that case go ahead and skip this step_

First we need to connect Snyk to GitHub so we can import our Repository. Do so by following these steps below:

* Login to http://app.snyk.io Sign up if you haven't already.
* Navigating to Integrations -> Source Control -> GitHub
* Fill in your Account Credentials to Connect your GitHub Account.

![alt tag](https://i.ibb.co/bPqqybM/snyk-starter-open-source-1.png)

<br />
<br />
<br />

# Snyk Code Steps

Snyk Code is developer-first, embedding SAST as part of the development process, enabling developers to build software securely during development, not trying to find and fix problems after the code is compiled. Snyk Code works in the IDEs and SCMs developers use to build and review software and provides fast, actionable, meaningful results to fix issues in real-time

## 3️⃣ - Step 3 - Enable Snyk Code within Snyk App

* Click on the "**Settings**" button on the top most navigation bar as shown below

![alt tag](https://i.ibb.co/3fS4VCd/snyk-code-1.png)

* Click on "**Snyk Code**", then enable it and click "**Save Changes**" as shown below

![alt tag](https://i.ibb.co/bP2FpGx/snyk-code-2.png)

## 4️⃣ - Step 4 - Add project to find Snyk Code Vulnerabilities

Now that Snyk is connected to your GitHub Account, import the Forked Repo "**juice-shop**" into Snyk as a Project.

* Navigate to Projects
* Click "**Add Project**" then select "**GitHub**"
* Click on the Repo you forked "**juice-shop**"
* Click "**Add Selected Repositories**"

![alt tag](https://i.ibb.co/ngxDfvw/Import-Juice-Shop.png)

* Once complete you should see a "**Code Analysis**" project as shown below

![alt tag](https://i.ibb.co/RpScxJ2/Snyk-Code-Results.png)

* Click on "**Code Analysis**" to view our SAST scan results

For each Vulnerability, Snyk displays the following:

1. Each Vulnerability grouped by severity
2. Each Vulnerability links to the CWE category code
3. Each Vulnerability shows the CWE category name
4. Displays the line of code where the security issue exists
5. Description for the issue and the code file name it exists in
6. A link to a Snyk Learn module on how to fix these type of vulnerabilities if available
7. The ability to ignore issues you wish to remove from the list

![alt tag](https://i.ibb.co/yk83tyP/Snyk-Code-vuln.png)

* Click on the "**Full Details**" button as shown below

Snyk products all provide a developer-friendly experience, so Snyk Code helps developers to quickly understand the problem, learn the background, and how to approach it. Snyk Code helps you understand the dangerous code flow step-by-step. For every issue, Code also provides a link to the lines in the relevant files, to view more details on the problem like the CWE, and how to approach it.

![alt tag](https://i.ibb.co/HnL22t7/Cross-site-scripting-Dataflow.png)

* Click on "**Fix Analysis**" to see how you can fix the issue based on other open source project. On this page you get not just source code example fixes but also the following detailed information

1. Details
2. Types Of Attacks
3. Affected Environments
4. How to prevent

![alt tag](https://i.ibb.co/M21xScH/Cross-site-scripting-Fix-Analysis.png)

## To Go Further with Snyk Code - Snyk Code workshop


Thanks for attending and completing this workshop

![alt tag](https://i.ibb.co/7tnp1B6/snyk-logo.png)

<hr />
Jenny Granja [jennifer.granja at snyk.io] is a Solution Engineer at Snyk APJ
Pas Apicella [pas at snyk.io] is a Principal Solution Engineer at Snyk APJ


