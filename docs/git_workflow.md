# JMT CI/CD Workflow

JMT uses our custom workflow for our CI/CD projects, as described below.

## Branches:
### Production
The production branch is the main branch in the repository. Code in this branch is 
automatically deployed into the production environment. 

Commits should never  be directly added to this branch. Instead, commit within 
a feature, bugfix, or hotfix branch, merge into staging for testing (where required)
and then merge into production. 

Code should only be merged into this branch when it has been properly tested and
determined to be stable. As such, this branch is considered stable.

### Staging
Code in the staging branch is automatically rolled out to the staging environment for testing.
Code should be merged into the staging branch to be tested when the developer feels it is 
ready to be deployed.

As with production, code should never be directly committed to this branch, instead, it
should be merged from a feature, bugfix, or hotfix branch.

Staging should never be directly deployed into Production. Instead, the feature, bugfix, 
and hotfix branches should be manually merged into production after they've been tested.

### Feature
Feature branches should be branched from the Production branch. They are where
active development of new features or improvements to existing features should take place.

Feature branches should start with `feature/`, and be followed by the GitHub issue
number and a brief description of the feature to be added. Example:
<br />`feature/#32_rate_limiting`

Feature branches should first be merged into Staging, to test and ensure they will not 
break the rest of the system, then they should be merged into Production, where they
will be deployed. All tests and checks should pass before merging.

### Bugfix
Bugfix branches should be branched from production. They are where bug fixes should be developed.

Bugfix branches should start with `bugfix/`, followed by the GitHub issue number and a brief
description of the bug. Example:
<br /> `bugfix/#33_rate_limit_crashes_client`

Bugfix branches should first be merged into Staging, to test and ensure they will not break
the rest of the system, then they should be merged into Production, where they will be deployed.
All tests and checks should pass before merging.

### Hotfix
Hotfix branches are where especially urgent fixes should be developed, since hotfix branches
are the only way to merge code directly into production without testing it in staging first.

Hotfix branches start with `hotfix/`, followed by the GitHub issue number, and
a brief description of the issue being fixed. Example:
<br /> `hotfix/#34_remote_code_execution`

Hotfixes should be merged directly into production. They should also be merged into staging, to
ensure that both branches are equal, but changes should go to production first.