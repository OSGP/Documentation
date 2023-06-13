<!--
SPDX-FileCopyrightText: Contributors to the GXF project

SPDX-License-Identifier: Apache-2.0
-->

# Contributing to documentation

## Documentation Publication

This documentation is available in multiple formats.

Web
* [Development branch publication](https://grid-exchange-fabric.gitbook.io/)

PDF
* Click on <B>Export as PDF</B> on right side of gitbook [Development branch publication](https://grid-exchange-fabric.gitbook.io/)

## Contributing to documentation

The documentation is build using GitBook software from Markdown files in the [documentation repository](https://github.com/OSGP/Documentation).

We encourage you to participate in improving the documentation. From corrected typos to new sections, every commit is appreciated. You can access the source files by clicking the "Fix this page"-button in the GitBook or by selecting the relevant Markdown-file in the documentation. You can commit your changes by sending a pull request.

1. Fork the repo, do work in a feature branch.
2. Issue a pull request.
3. Make sure the automated test suite succeeds. They will show-up in the pull request.
4. Sign the CLA using [EasyCLA](https://lfcla.com/).
5. Assign a maintainer or other developer on this topic to accept/evaluate your pull request. The current maintainer can be found in the [governance paragraph](governance.md).

Some information on GitBook and using Markdown can be found [here](http://help.gitbook.com/), more elaborate information on GitHub-flavored Markdown is found [here](https://help.github.com/articles/github-flavored-markdown/). If you like to upload illustration, you can use git or [Github](https://help.github.com/articles/adding-a-file-to-a-repository/)

If you are completely new to this and you need help to get started, file an issue in the documentation repository.

### Chapters in the documentation

It may be obvious to you already from the index, however, here is an overview on what documentation goes in which chapter.

* Chapter 1 consist of an open smart grid platform introduction and architecture for potential users, architects and developers. The open smart grid platform website is used for basic product information.
* Chapter 2 contains the general userguide for open smart grid platform users
* Chapter 3 contains community related topics
* Chapter 4 contains information related to the open smart grid platform domains
* Chapter 5 contains information related to the protocols and simulators
* Chapter 6 shows the support options
* Chapter 7 code and documentation license

### Versioning within the documentation

We have chosen to work with GitBook since it allows us to make different versions of documentation for each release. This is done by branching the files in the documentation repository. The master branch is used for releases only. The development branch is our main and current branch. If you like to improve the documentation, start a feature branch with your changes and send a pull request to the development branch.

### Guidelines for new documentation

* The master branch is only used by major open smart grid platform releases
* Don't commit directly to the development branch, please do a pull request.
* We use the American spelling
* Please follow the used chapter and section numbering and apply it in your commits as well
* Currently we do not use image numbering, since it is too much of a hassle to keep it up-to-date. If you have a smart idea to do this, let us know!
* Give your \(sub\) document a relevant name or section with number
* Update SUMMARY.md if needed

### Documentation inspiration

Inspiration on how to write good documentation can be found here: [http://docs.writethedocs.org/](http://docs.writethedocs.org/).

