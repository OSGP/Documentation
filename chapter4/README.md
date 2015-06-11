# CHAPTER 4. Open Source and Community

We invite everyone to participate in the development of OSGP. There are multiple ways to support the project.

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

Anyone can send in a pull request. Once you send in a pull request, our developers will check your commit and test it. You can view the SonarCube test results at (http://54.77.62.182/sonarqube/) and the Jenkins continuous integration results at (http://54.77.62.182/) 

If your code is a useful contribution and meets our quality standards (see section 3.1), it will be added to the OSGP! Our developers are in charge of judging this. 

## 4.3 Contributor License Agreement

We ask each of our contributors to sign our contributor license agreement (CLA). This has advantages for both parties, it gives you the ensurance that your contribution will remain available under the Apache 2.0 license. Meanwhile, you give your code in license to us, so we can add your code to OSGP. And we know your contribution is entirely your work, so we don't get in trouble with legal issues. Please read the CLA text carefully.  

## 4.4 Issues and Bug Report

Issues are used for communicating:
- Development idea's
- Bug reports
- Questions
- ...

Issues and bugs can be post using the issue tracker of the relevant repository. 

### 4.4.1 Bug tracking

1. Find out as much as possible about the bug before reporting it. Please check on GitHub whether the bug has already been reported. Also, look for logs, error messages etc. Please include as much information as possible background on the bug. 
2. The maintainer makes sure that somebody will look at the bug, check for duplicates and thank the contributor for sending in the bug. If the bug turns out to be a duplicate, the issue will be closed.
3. A developer will try to reproduce the bug and will look for the root cause. The developer adds his findings to the issue. If the developer can not reproduce the bug, the developer will contact the user for more information or/and login into the user's system (when possible for the user/developer). If it's impossible to re-produce the bug, the issue will be closed.
4. Otherwise, the developer will write a patch and tests the fix.
5. Once the patch is accepted (see Code review/test process), it will be shipped with the next release.
6. The maintainer than closes the issue.

### 4.4.2 New features 

1. If there is a need (or wish!) for a new feature, add it as issue to the relevant repository. Please provide a full description about the problem and the potential feature. If you use one of the following links, you will be given a basic format for your issue. 

* [Issue in Platform](https://github.com/OSGP/Platform/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in Shared repo](https://github.com/OSGP/shared/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in Protocol-Adapter-OSLP](https://github.com/OSGP/Protocol-Adapter-OSLP/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in Protocol-Adapter-DLMS](https://github.com/OSGP/Protocol-Adapter-DLMS/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in Config](https://github.com/OSGP/Config/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in Integration-Tests](https://github.com/OSGP/Integration-Tests/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)
* [Issue in the documentation](https://github.com/OSGP/documentation/issues/new?title=Feature%20request:My%20Title&body=**Use%20case(s):**%0A%0A**Expected%20behavior:**%0A%0A**Motivation:**%0A%0A**Acceptance%20criteria:**)

2. A developer can take on the issue and start working on it on voluntary base. If you need this feature and you have the money to pay for it, you can hire a developer and have the developer work on it. If OSGP core components are involved, please discuss your change first with one of our maintainers.

3. The developer makes a description on how he wants to fix the problem. Other developers can discuss the solution as well. If everybody agrees on the solution direction, the developer codes the solution and submits it (by sending in a pull request). The developer should also document the feature in the [GitBook](https://github.com/OSGP/Documentation/tree/development)

4. The maintainer can check the code (or assign this to someone else) and merge it with upstream releases.

## 4.5 Governance

//TODO

## 4.6 Code of Conduct

Like the technical community as a whole, the OSGP team and community is made up of a mixture of professionals and volunteers from all over the world, working on every aspect of the mission - including mentorship, teaching, and connecting people.

Diversity is one of our huge strengths, but it can also lead to communication issues and unhappiness. To that end, we have a few ground rules that we ask people to adhere to. This code applies equally to founders, mentors and those seeking help and guidance.

This isn’t an exhaustive list of things that you can’t do. Rather, take it in the spirit in which it’s intended - a guide to make it easier to enrich all of us and the technical communities in which we participate.

This code of conduct applies to all spaces managed by the OSGP project (or OSGP Software Foundation onces established). This includes IRC, the mailing lists, the issue tracker, DSF events, and any other forums created by the project team which the community uses for communication. In addition, violations of this code outside these spaces may affect a person's ability to participate within them.

If you believe someone is violating the code of conduct, we ask that you report it by emailing opensource@smartsocietyservices.com. 

#### Be friendly and patient.

#### Be welcoming. 
We strive to be a community that welcomes and supports people of all backgrounds and identities. This includes, but is not limited to members of any race, ethnicity, culture, national origin, colour, immigration status, social and economic class, educational level, sex, sexual orientation, gender identity and expression, age, size, family status, political belief, religion, and mental and physical ability.

#### Be considerate. 
Your work will be used by other people, and you in turn will depend on the work of others. Any decision you take will affect users and colleagues, and you should take those consequences into account when making decisions. Remember that we're a world-wide community, so you might not be communicating in someone else's primary language.

#### Be respectful. 
Not all of us will agree all the time, but disagreement is no excuse for poor behavior and poor manners. We might all experience some frustration now and then, but we cannot allow that frustration to turn into a personal attack. It’s important to remember that a community where people feel uncomfortable or threatened is not a productive one. Members of the OSGP community should be respectful when dealing with other members as well as with people outside the OSGP community.

#### Be careful in the words that you choose. 
We are a community of professionals, and we conduct ourselves professionally. Be kind to others. Do not insult or put down other participants. Harassment and other exclusionary behavior aren't acceptable. This includes, but is not limited to:
- Violent threats or language directed against another person.
- Discriminatory jokes and language.
- Posting sexually explicit or violent material.
- Posting (or threatening to post) other people's personally identifying information ("doxing").
- Personal insults, especially those using racist or sexist terms.
- Unwelcome sexual attention.
- Advocating for, or encouraging, any of the above behavior.
- Repeated harassment of others. In general, if someone asks you to stop, then stop.

#### When we disagree, try to understand why. 
Disagreements, both social and technical, happen when people get passionate about what they are doing. It is important that we resolve disagreements and differing views constructively. Remember that we’re different. The strength of OSGP comes from its varied community, people from a wide range of backgrounds. Different people have different perspectives on issues. Being unable to understand why someone holds a viewpoint doesn’t mean that they’re wrong. Don’t forget that it is human to err and blaming each other doesn’t get us anywhere. Instead, focus on helping to resolve issues and learning from mistakes.

_This Code of Conduct is based on the Django Code of Conduct_

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

### 4.8.4 Adding picture using the GitHub web interface

People using the GitHub web interface can use [this method](http://solutionoptimist.com/2013/12/28/awesome-github-tricks/) to upload pictures to GitHub. How to consequently add the picture to the document can be found in the [GitBook Help](http://help.gitbook.com/)

## 4.9 Foundation

//TODO
