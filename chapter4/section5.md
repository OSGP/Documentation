## 4.5 Contributing to documentation

Our most recent documentation can be found [here](http://54.77.62.182/documentation/) The documentation is build using GitBook software from Markdown files in the [documentation repository](https://github.com/OSGP/Documentation). 

We encourage you to participate in improving the documentation. From corrected typos to new sections, every commit is appreciated. You can access the source files by clicking the "Fix this page"-button in the GitBook or by selecting the relevant Markdown-file in the documentation. You can commit your changes by sending a pull request. 

1. Fork the repo, do work in a feature branch.
2. Issue a pull request.
3. Make sure the automated test suite succeeds. They will show-up in the pull request.
4. Sign the CLA using [cla-assistant](http://52.16.237.165/) (a comment by CLAAdmin will appear for your pull request to help you out).
5. Assign a maintainer to accept/evaluate your pull request. The current maintainer can be found in the [documentation](http://54.77.62.182/documentation/chapter4/section3.html).

Some information on GitBook and using Markdown can be found [here](http://help.gitbook.com/), more elaborate information on GitHub-flavored Markdown is found [here](https://help.github.com/articles/github-flavored-markdown/). If you like to upload illustation, you can use git or [Github](https://help.github.com/articles/adding-a-file-to-a-repository/)

If you are completely new to this and you need help to get started, fire an issure in the documenation repository.

### 4.5.1 Chapters in the documentation

It may be obvious to you already from the index, however, here is an overview on what documentation goes in which chapter. 

Chapter 1 consist of an OSGP introduction and architecture for potential users, architects and developers. The OSGP website is used for basic product information.
Chapter 2 containts documentantation for OSGP users
Chapter 3 consist of developer information for all sorts of developers
Chapter 4 contains community related topics
Chapter 5 shows the support options
Chapter 4 the code and documentation license

### 4.5.2 Versioning within the documentation

We have chosen to work with GitBook since it allows us to make different versions of documentation for each release. This is done by branching the files in the documentation repository. The master branch is used for releases only. The development branch is our main and current branch. If you like to improve the documentation, start a feature branch with your changes and send a pull request to the development branch.

### 4.5.3 Guidelines for new documentation

- The master branch is only used by major OSGP releases
- Don't commit directly to the development branch, please do a pull request.
- We use the American spelling
- Please follow the used chapter and section numbering and apply it in your commits as well
- Currently we do not use image numbering, since it is too much of a hassle to keep it up-to-date. If you have a smart idea to do this, let us know! 
- Give your (sub) document a relevant name or section with number
- Update SUMMARY.md if needed

### 4.5.4 Documentation inspiration

Inspiration on how to write good documentation can be found here: [http://docs.writethedocs.org/](http://docs.writethedocs.org/).

