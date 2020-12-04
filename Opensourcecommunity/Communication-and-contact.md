## Communication and Contact

We choose [Jira](https://smartsocietyservices.atlassian.net/projects/OC/issues/) for most of our development communication. This keeps the communication central and topic central and connect to development effort. 
Please use [Jira](https://smartsocietyservices.atlassian.net/projects/OC/issues/) for issues and bugs. 

If you want to get in touch to discuss non-technical subjects, send us an email to the LF energy GXF mailing list gxf@lists.lfenergy.org or open an [issue on Github](https://github.com/OSGP/documentation/issues/new?title=Question%20:My%20Title&body=**Question:**%0A%0A**background:**%0A%0A**).

## Jira

Jira was chosen due to its extensive features. The current [Jira](https://smartsocietyservices.atlassian.net/projects/OC/issues/) board is sponsored by Alliander for synergy reasons. 
Once we have multiple contributors outside Alliander we can move to a dedicated Jira instance or something else.

Once you get actively involved, you can request write permissions on the Jira board.
You can request write access to the Jira issue board by sending a request to gxf@lists.lfenergy.org.

### New Features

1. If there is a need (or wish!) for a new feature, add it as issue to [Jira](https://smartsocietyservices.atlassian.net/projects/OC/issues/) as a user story. Please provide a full description about the background of the problem. Spilt-up big user stories in multiple small user stories.

2. A developer can take on the issue and start working on it on voluntary base. If you need this feature and you have the money to pay for it, you can hire a developer and have the developer work on it. If open smart grid platform core components are involved, please discuss your change first with one of the developers/maintainers.

3. The developer makes a description on how he wants to fix the problem. Other developers can discuss the solution as well. If everybody agrees on the solution direction, the developer codes the solution and submits it (by sending in a pull request). The developer should also document the feature in the [GitBook](https://github.com/OSGP/Documentation/tree/development)

4. The maintainer can check the code (or assign this to someone else) and merge it with upstream releases.

### Bug tracking

1. Find out as much as possible about the bug before reporting it. Please check on GitHub/Jira whether the bug has already been reported. Also, look for logs, error messages etc. Please include as much information as possible background on the bug and submit the bug on Github or Jira. 
2. The maintainer makes sure that somebody will look at the bug, check for duplicates and thank the contributor for sending in the bug. If the bug turns out to be a duplicate, the issue will be closed.
3. A developer will try to reproduce the bug and will look for the root cause. The developer adds his findings to the issue. If the developer cannot reproduce the bug, the developer will contact the user for more information or/and login into the user's system (when possible for the user/developer). If it's impossible to re-produce the bug, the issue will be closed.
4. Otherwise, the developer will write a patch and tests the fix.
5. Once the patch is accepted (see Code review/test process), it will be shipped with the next release.
6. The maintainer than closes the issue.

### Questions
If you have a question, please create an Github issue in the [documentation repository](https://github.com/OSGP/documentation/issues/new?title=Question%20:My%20Title&body=**Question:**%0A%0A**background:**%0A%0A**) or request access to [Jira](https://smartsocietyservices.atlassian.net/projects/OC/issues/).

 
### Report security issues
Due to the sensible nature of security issues e.g. zero days, we prefer a responsible disclosure. Security issues can be reported to [gxf+owner@lists.lfenergy.org](mailto:gxf+owner@lists.lfenergy.org).
