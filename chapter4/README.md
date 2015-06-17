# CHAPTER 4. Open Source and Community

We invite anyone to participate in the development of OSGP. There are multiple ways to support the project.

- submit issues about bugs or requested features
- solve issues
- develop new features
- write or improve the documentation

This chapter contains all the non-technical knowledge for developers to start contributing.

## 4.1 Submitting code

To submit changes to the OSGP branch:
1. Create a fork of the OSGP repo you will be working in
2. Make and commit your changes to your fork
3. Create a pull request to merge the changes into the right branch (see 4.2.1 for the branching strategy)
If the changes fixes a bug, mention the issue number in the commit message or pull request message (example: fixes
101, solved 87). If no ticket exists, create one beforehand. Afterwards, please update the relevant documentation in this GitBook.

### 4.1.1 Open Source Branching Strategy

The OSGP's main branch is master. All major releases are tagged in this branch. Development is done in
the development and feature branches. We use the GitFlow branching strategy. Find more information on this strategy here: [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/)

The GitFlow work flow is someone complicated, but it has the advantage that it gives a clear overview of all previous releases and current development and thus helps to collaborate more efficiently. Please follow this strategy in your commits.

### 4.1.2 Guidelines

Before code is merged it needs to comply with a number of guidelines:
1. Code should be as complete as possible (No placeholders, TODO's or FIXME's)
2. Right formatting; code should follow the Coding Conventions (see 3.1.2)
3. Fixed/added unit tests where applicable
4. Javadocs added where applicable

## 4.2 Pull requests: review process

Once you send in a pull request, our developers will check your commit and test it. You can view the SonarCube test results at (http://54.77.62.182/sonarqube/) and the Jenkins continuous integration results at (http://54.77.62.182/) 

If your code is a useful contribution and meets our quality standards (see section 3.1), it will be added to the OSGP! Our developers are in charge of judging this. 

## 4.3 Contributor License Agreement

We ask each of our contributors to sign our contributor license agreement (CLA). This has advantages for both parties, it gives you the ensurance that your contribution will remain available under the Apache 2.0 license. Meanwhile, you give your code in license to us, so we can add your code to OSGP. And we know your contribution is entirely your work, so we don't get in trouble with legal issues. Please read the CLA text carefully.  

## 4.4 Issues and Bug Report

Issues are used for communicating:
- Development idea's
- Bug reports
- Questions
- ...
//TODO

## 4.5 Governance

//TODO

With OSGP we intend to have the right balance between a benevolent Dictator and a Formal Metitocracy to prevent unwanted dictators and ever lasting discussions. The basic idea is to make dicissions based on concensus. If this takes to long, the community council can be asked to make a decission.



Community council
This council can make disccions on all commmunity related subject. The community council can be elected by the community members (when the need is theire). The community council consists of 5 people. 1 is seat is taken by the OSGP Foundation for alligntment between the foundation and the online community.

General goverance
- Make sure that people can contribute
- How people can contribute
- Infrastructure choices
- Community wide principles
- Procedures
- Governance itself

Direction governance
- Decissions about goals and ambitions
- adress concerns

Maintainers
Maintainers are responsible for maintaing parts of the code-base. Maintainers have the following responsibitlities
- Coordinate development activity
- Make sure code reviews are being done
- Eveluate pull-requests
- Coordinate bug follow-ups
In case of long discussions or arguments, maintainers or other can request a community coucil decission.

## 4.6 Code of Conduct

Please treat everyone with respect :)
//TODO

## 4.7 Communication and Contact

For issues and bugs, please use our GitHub issue list, we are currently actively developing the Open Smart Grid Platform, so your message will be detected in no-time. If you want to get in touch to discuss to discuss non-technical subjects, send us an email to our temporary email address at opensource@smartsocietyservices.com. Once we get the foundation going, we will open an address so you can directly contact one of the foundation's employees.

## 4.8 Contributing to documentation

Our most recent documentation can be found [here](http://54.77.62.182/job/OSGP_Documentation_development/lastSuccessfulBuild/artifact/_book/index.html) The documentation is build using GitBook software from Markdown files in the [documentation repository](https://github.com/OSGP/Documentation). 

We encourage you to participate in improving the documentation. From corrected typos to new sections, every commit is appreciated. You can access the source files by clicking the "Fix this page"-button in the GitBook or by selecting the relevant Markdown-file in the documentation. You can commit your changes by sending a pull request. 

Some information on GitBook and using Markdown can be found [here](http://help.gitbook.com/), more elaborate information on GitHub-flavored Markdown is found [here](https://help.github.com/articles/github-flavored-markdown/). If you are completely new to this and you need help to get started, don't worry (so was I...), just send us an email at opensource@smartsocietyservices.com

### 4.8.1 Chapters in the documentation

It may be obvious to you already from the index, however, here is an overview on what documentation goes in which chapter. //TODO

### 4.8.2 Versioning withing the documentation

We have chosen to work with GitBook since it allows us to make different versions of documentation for each release. This is done by branching the files in the documentation repository. //TODO

//TODO

### 4.8.3 Guidelines for new documentation

- We use the American spelling
- Please follow the used chapter and section numbering and apply it in your commits as well
- Currently we do not use image numbering, since it is to much of a hassle to keep it up-to-date. If you have a smart idea to do this, let us know! 

## 4.9 Foundation

//TODO
