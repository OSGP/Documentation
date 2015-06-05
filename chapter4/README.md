# CHAPTER 4. Open Source and Community

Non-technical knowledge for developers.

## 4.1 Foundation

//TODO

## 4.2 Open Source Branching Strategy

We use the GitFlow branching strategy. Find more information on this strategy here: [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/)

The GitFlow work flow is someone complicated, but it has the advantage that it gives a clear overview of all previous releases and current development and thus helps to collaborate more efficiently. Please follow this strategy in your commits. 
## 4.3 Pull requests: review process

Once you send in a pull request, our developers will check your commit and test it. You can view the SonarCube test results at (http://54.77.62.182/sonarqube/) and the Jenkins continuous integration results at (http://54.77.62.182/) 

If your code is a useful contribution and meets our quality standards (see section 3.1), it will be added to the OSGP! Our developers are in charge of judging this. 

## 4.4 Contributor License Agreement

We ask each of our contributors to sign our contributor license agreement (CLA). This has advantages for both parties, it gives you the ensurance that your contribution will remain available under the Apache 2.0 license. Meanwhile, you give your code in license to us, so we can add your code to OSGP. And we know your contribution is entirely your work, so we don't get in trouble with legal issues. Please read the CLA text carefully.  

## 4.5 Issues and Bug Report

Issues are used for communicating:
- Development idea's
- Bug reports
- Questions
- ...
//TODO

## 4.6 Governance

//TODO

## 4.7 Code of Conduct

Please treat everyone with respect :)
//TODO

## 4.8 Communication and Contact

For issues and bugs, please use our GitHub issue list, we are currently actively developing the Open Smart Grid Platform, so your message will be detected in no-time. If you want to get in touch to discuss to discuss non-technical subjects, send us an email to our temporary email address at opensource@smartsocietyservices.com. Once we get the foundation going, we will open an address so you can directly contact one of the foundation's employees.

## 4.9 Contributing to documentation

Our most recent documentation can be found [here](http://54.77.62.182/job/OSGP_Documentation_development/lastSuccessfulBuild/artifact/_book/index.html) The documentation is build using GitBook software from Markdown files in the [documentation repository](https://github.com/OSGP/Documentation). 

We encourage you to participate in improving the documentation. From corrected typos to new sections, every commit is appreciated. You can access the source files by clicking the "Fix this page"-button in the GitBook or by selecting the relevant Markdown-file in the documentation. You can commit your changes by sending a pull request. 

Some information on GitBook and using Markdown can be found [here](http://help.gitbook.com/), more elaborate information on GitHub-flavored Markdown is found [here](https://help.github.com/articles/github-flavored-markdown/). If you are completely new to this and you need help to get started, don't worry (so was I...), just send us an email at opensource@smartsocietyservices.com

### 4.9.1 Chapters in the documentation

It may be obvious to you already from the index, however, here is an overview on what documentation goes in which chapter. //TODO

### 4.9.2 Versioning withing the documentation

We have chosen to work with GitBook since it allows us to make different versions of documentation for each release. This is done by branching the files in the documentation repository. //TODO

//TODO

### 4.9.3 Guidelines for new documentation

- We use the American spelling
- Please follow the used chapter and section numbering and apply it in your commits as well
- Currently we do not use image numbering, since it is to much of a hassle to keep it up-to-date. If you have a smart idea to do this, let us know! 
