# Snyk Code and Snyk Open Source Workshop

Snyk Code and Snyk Open Source together provide easy-to-use, fast and accurate SAST and SCA testing, enabling developers and security teams to easily find and fix both security issues in their own proprietary code as well as known vulnerabilities in their open source dependencies, reducing risk and improving the pace of development

## Prerequisites

* public GitHub account - http://github.com
* git CLI - https://git-scm.com/downloads
* snyk CLI - https://support.snyk.io/hc/en-us/articles/360003812538-Install-the-Snyk-CLI
* Registered account on Snyk App - http://app.snyk.io

## What we will do in this hands-on workshop?

In this hands-on workshop we will achieve the following:

* [Step 1 - Fork the highly vulnerable Juice-Shop Application](#step-1---fork-the-highly-vulnerable-juice-shop-application)
* [Step 2 - Configure GitHub Integration](#step-2---configure-github-integration)

Snyk Code steps

* [Step 3 - Enable Snyk Code within Snyk App](#step-3---enable-snyk-code-within-snyk-app)
* [Step 4 - Add project to find Snyk Code Vulnerabilities](#step-4---add-project-to-find-snyk-code-vulnerabilities)
* [Step 5 - Run a Snyk Code CLI Test](#step-5---run-a-snyk-code-cli-test)

Snyk Open Source steps

* [Step 6 - Find vulnerabilities](#step-6---find-vulnerabilities)
* [Step 7 - Fix using a Pull Request](#step-7---fix-using-a-pull-request)
* [Step 8 - Run a Snyk CLI Test](#step-8---run-a-snyk-cli-test)

# Workshop Steps

_Note: It is assumed your using a mac for these steps, but it should also work on Windows or linux with some modifications to the scripts potentially_

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

# Snyk Code Steps

Snyk Code is developer-first, embedding SAST as part of the development process, enabling developers to build software securely during development, not trying to find and fix problems after the code is compiled. Snyk Code works in the IDEs and SCMs developers use to build and review software and provides fast, actionable, meaningful results to fix issues in real-time

## Step 3 - Enable Snyk Code within Snyk App

* Click on the "**Settings**" button on the top most navigation bar as shown below

![alt tag](https://i.ibb.co/3fS4VCd/snyk-code-1.png)

* Click on "**Snyk Code**", then enable it and click "**Save Changes**" as shown below

![alt tag](https://i.ibb.co/bP2FpGx/snyk-code-2.png)

## Step 4 - Add project to find Snyk Code Vulnerabilities

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

## Step 5 - Run a Snyk Code CLI Test

In addition to the Snyk App UI we also have, snyk - CLI a build-time tool to find & fix known vulnerabilities in open-source dependencies, IaC configuration files and SAST scans on the source code files itself (Snyk Code).

* Before we get started please make sure you have setup the Snyk CLI. There are various install options as per the links below. Using the prebuilt binaries means you don't have to install NPM to install the Snyk CLI.

1. Install Page - https://support.snyk.io/hc/en-us/articles/360003812538-Install-the-Snyk-CLI
2. Prebuilt Binaries - https://github.com/snyk/snyk/releases

_Note: Please ensure you have the latest version of the Snyk CLI installed a version equal to or greater than the version below_

```bash
$ snyk --version
1.801.0
```

* Authorize the Snyk CLI with your account as follows

```bash
$ snyk auth

Now redirecting you to our auth page, go ahead and log in,
and once the auth is complete, return to this prompt and you'll
be ready to start using snyk.

If you can't wait use this url:
https://snyk.io/login?token=ff75a099-4a9f-4b3d-b75c-bf9847672e9c&utm_medium=cli&utm_source=cli&utm_campaign=cli&os=darwin&docker=false

Your account has been authenticated. Snyk is now ready to be used.
```

* Clone your forked repository as shown below. You can use your own GitHub forked repo here instead of the one shown below if you like

```shell
$ git clone https://github.com/JennySnyk/juice-shop
Cloning into 'juice-shop'...
remote: Enumerating objects: 94967, done.
remote: Counting objects: 100% (17/17), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 94967 (delta 5), reused 13 (delta 4), pack-reused 94950
Receiving objects: 100% (94967/94967), 157.66 MiB | 10.35 MiB/s, done.
Resolving deltas: 100% (72676/72676), done.
```

* Change to the "**juice-shop**" directory

```shell
$ cd juice-shop
```

* At this point let's go ahead and run our first "**snyk code test**" as shown below

```shell
$ snyk code test

Testing /Users/pasapicella/snyk/SE/workshops/SCA-SAST-workshop/juice-shop ...

 ✗ [Low] Cleartext Transmission of Sensitive Information
     Path: test/e2eSubfolder.js, line 7
     Info: http (used in require) is an insecure protocol and should not be used in new code.

 ✗ [Low] Cleartext Transmission of Sensitive Information
     Path: test/api/productReviewApiSpec.js, line 9
     Info: http (used in require) is an insecure protocol and should not be used in new code.

...

 ✗ [High] Server-Side Request Forgery (SSRF)
     Path: routes/profileImageUrlUpload.js, line 19
     Info: Unsanitized input from the HTTP request body flows into request.get, where it is used as an URL to perform a request. This may result in a Server-Side Request Forgery vulnerability.

 ✗ [High] Server-Side Request Forgery (SSRF)
     Path: frontend/src/app/Services/configuration.service.ts, line 111
     Info: Unsanitized input from data from a remote resource flows into get, where it is used as an URL to perform a request. This may result in a Server-Side Request Forgery vulnerability.

 ✗ [High] Improper Neutralization of Directives in Statically Saved Code
     Path: routes/userProfile.js, line 46
     Info: Unsanitized input from cookies flows into pug.compile, where it is used to construct a template that gets rendered. This may result in a Server-Side Template Injection vulnerability.


✔ Test completed

Organization:      undefined
Test type:         Static code analysis
Project path:      /Users/pasapicella/snyk/SE/workshops/SCA-SAST-workshop/juice-shop

199 Code issues found
25 [High]  17 [Medium]  157 [Low]

```

### To Go Further with Snyk Code - Snyk Code workshop

Finally, to go further, feel free to look at this workshop https://github.com/papicella/snyk-code-workshop where additional steps are available (Snyk Code CLI Test and Snyk Code Test using VS Code)

# Snyk Open Source Steps

Snyk Open Source is a Software Composition Analysis took which seamlessly and proactively finds, prioritizes and fixes vulnerabilities and license violations in open source dependencies

## Step 6 - Find vulnerabilities

* Since Juice-Shop project had been imported in the Step 3, you should see multiple "**package.json**" projects as shown below.

![alt tag](https://i.ibb.co/d4Qb3TV/Snyk-OS-vuln.png)

* Click on the second "**package.json**" to view our Open Source scan results

First let's explore the Juice-Shop project risks by clicking on the "**package.json**" file which is the manifest file where the open source dependencies are declared.

![alt tag](https://i.ibb.co/ZhN6tXY/Package-json-view.png)

Thenk go back on the Snyk WebUI and let's have a look at the vulnerabilities.

For each Vulnerability, Snyk displays the following ordered by our [Proprietary Priority Score](https://docs.snyk.io/features/fixing-and-prioritizing-issues/starting-to-fix-vulnerabilities/snyk-priority-score) :
1. The module that introduced it and, in the case of transitive dependencies, its direct dependency,
1. Details on the path and proposed Remediation, as well as the specific vulnerable functions
1. Overview
1. Exploit maturity
1. Links to CWE, CVE and CVSS Score
1. Plus more ...

![alt tag](https://i.ibb.co/xq2GWCs/Snyk-OS-vuln.png)

## Step 7 - Fix using a Pull Request

When using the GitHub integration, and if a fix is available, Snyk can automatically upgrade the vulnerable dependency to a non-vulnerable version through a Pull Request.

* Click on "**Fix this vulnerability**" for "**Prototype Pollution**" issue as shown below

![alt tag](https://i.ibb.co/9NHPmn2/Snyk-OS-Fix-this-vuln.png)

* On the next screen, you'll be able to confirm the issue to fix with this PR. Click "**Open a Fix PR**"

![alt tag](https://i.ibb.co/y5PHhhT/Vulns-to-fix-pr-view.png)
![alt tag](https://i.ibb.co/p2Lx5Rd/Open-fix-pr-button.png)

* Once it's ready, you'll be taken to the PR in GitHub, where you can review the changes in the file diff view:

Snyk integrates with your preferred Git repository to scan your manifest files for any new code and potential vulnerabilities whenever you submit a pull request (PR), protecting the security of your code before you ever merge it with the main branch

![alt tag](https://i.ibb.co/ySc72zN/Fix-PR-Github.png)

* We see that CI checks completed successfully, assuring us we didn't introduce a breaking change

![alt tag](https://i.ibb.co/BzrNHvg/Files-changed-Github.png)

* Optionally now, go ahead and merge the PR!
* Back in Snyk we can appreciate that our package.json file has 1 less Critical Severity Vulnerability if you did fix it

### Step 8 - Run a Snyk CLI Test

In addition to the Snyk App UI we also have, snyk - CLI and build-time tool to find & fix known vulnerabilities in open-source dependencies. The CLI is what is used in DevOps pipelines to introduce Application Security Scans as part of that workflow to push applications into production.

* Before we get started please make sure you have setup the Snyk CLI. There are various install options as per the links below. Using the prebuilt binaries means you don't have to install NPM to install the Snyk CLI.

1. Install Page - https://support.snyk.io/hc/en-us/articles/360003812538-Install-the-Snyk-CLI
1. Prebuilt Binaries - https://github.com/snyk/snyk/releases

* In order to run a Snyk CLI test we must install the npm packages so if you have npm in your path you can install them as follows

```shell
$ npm install
```

_Note: If you don't have npm installed this you can skip this final step as a "snyk test" will not work without a **package-lock.json** file or the "**node_modules**" folder_

* Once npm is installed run a Snyk CLI test as follows

```shell
❯ snyk test --all-projects

Testing /Users/pasapicella/snyk/SE/workshops/SCA-SAST-workshop/juice-shop...

Tested 898 dependencies for known issues, found 37 issues, 52 vulnerable paths.


Issues to fix by upgrading:

  Upgrade concurrently@5.3.0 to concurrently@6.0.0 to fix
  ✗ Regular Expression Denial of Service (ReDoS) [High Severity][https://snyk.io/vuln/SNYK-JS-ANSIREGEX-1583908] in ansi-regex@4.1.0
    introduced by concurrently@5.3.0 > yargs@13.3.2 > string-width@3.1.0 > strip-ansi@5.2.0 > ansi-regex@4.1.0 and 8 other path(s)

  Upgrade express-jwt@0.1.3 to express-jwt@6.0.0 to fix
  ✗ Regular Expression Denial of Service (ReDoS) [Low Severity][https://snyk.io/vuln/npm:moment:20170905] in moment@2.0.0
    introduced by express-jwt@0.1.3 > jsonwebtoken@0.1.0 > moment@2.0.0
    
...

  ✗ Use After Free [High Severity][https://snyk.io/vuln/SNYK-JS-NODESASS-541000] in node-sass@4.14.1
    introduced by node-sass@4.14.1
  No upgrade or patch available
  ✗ Out-of-bounds Read [Medium Severity][https://snyk.io/vuln/SNYK-JS-NODESASS-541002] in node-sass@4.14.1
    introduced by node-sass@4.14.1
  No upgrade or patch available


License issues:

  ✗ GPL-3.0 license (new) [High Severity][https://snyk.io/vuln/snyk:lic:npm:qrious:GPL-3.0] in qrious@4.0.2
    introduced by anuglar2-qrcode@2.0.9998 > qrious@4.0.2



Organization:      pas.apicella-41p
Package manager:   npm
Target file:       frontend/package.json
Project name:      frontend
Open source:       no
Project path:      /Users/pasapicella/snyk/SE/workshops/SCA-SAST-workshop/juice-shop
Licenses:          enabled

Tip: Run `snyk wizard` to address these issues.


Tested 2 projects, 2 contained vulnerable paths.

```

### To Go Further with Snyk Open Source - Snyk Open Source workshop

Finally, to go further, feel free to look at this workshop https://github.com/papicella/snyk-open-source-workshop where additional steps are guided (Testing using the Snyk CLI and the IDE Integration with VS Code)



Thanks for attending and completing this workshop

![alt tag](https://i.ibb.co/7tnp1B6/snyk-logo.png)

<hr />
Jenny Granja [jennifer.granja at snyk.io] is a Solution Engineer at Snyk APJ 
<br/>
Pas Apicella [pas at snyk.io] is a Principal Solution Engineer at Snyk APJ


