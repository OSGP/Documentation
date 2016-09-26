## Contributing to the code

Thank you for contributing to the Open Smart Grid Platform. Please keep the following in mind before submitting code. 

### Guidelines

Before code is merged it needs to comply with a number of guidelines:
1. Code should be as complete as possible (preferably no placeholders, TODO's or FIXME's)
2. Right formatting; code should follow the Coding Conventions (see 3.1.2)
3. Fixed/added unit tests where applicable
4. Javadocs added where applicable
5. Accepting pull-requests with SonarQube reports "Blocker" and "Critical" and are not allowed
6. Comply with International open standards where possible (e.g. IEC standards)

### Contributor License Agreement

We ask each of our contributors to sign our contributor license agreement (CLA). This has advantages for both parties, it gives you the assurance that your contribution will remain available under the Apache 2.0 license. Meanwhile, you give your code in license to us, so we can add your code to the open smart grid platform. And we know your contribution is entirely your work, so we don't get in trouble with legal issues. Please read the CLA text carefully.  

### Submitting code

To submit changes to the open smart grid platform branches:
1. Create a fork of the open smart grid platform repo you will be working in
2. Make and commit your changes to your fork
3. Create a pull request to merge the changes into the right branch (see 4.1.4 for the branching strategy)
If the changes fix a bug, mention the issue number in the commit message or pull request message (example: fixes
101, solved 87). If no ticket exists, create one beforehand. Afterwards, please update the relevant documentation in this GitBook.

### Open Source Branching Strategy

The open smart grid platform's main branch is master. All major releases are tagged in this branch. Development is done in
the development and feature branches. We use the GitFlow branching strategy. Find more information on this strategy here: [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/)

The GitFlow work flow is someone complicated, but it has the advantage that it gives a clear overview of all previous releases and current development and thus helps to collaborate more efficiently. Please follow this strategy in your commits.

### Pull requests: review process

Anyone can send in a pull request. Once you send in a pull request, assign a maintainer to accept/evaluate your pull request. You can view the SonarCube test results at (http://ci.opensmartgridplatform.org/sonarqube/) and the Jenkins continuous integration results at (http://ci.opensmartgridplatform.org) 

If your code is a useful contribution and meets our quality standards (see section 3.1), it will be added to the open smart grid platform! Developers are in charge of judging this. Don't forget to update the documentation as well.
