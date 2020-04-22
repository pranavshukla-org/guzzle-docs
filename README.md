
## Contributor's guide

### Setting up workspace of a contributor

1. Ensure you have the latest version of Node (https://nodejs.org/en/download/) installed. We also recommend you install Yarn (https://yarnpkg.com/en/docs/install) as well. You have to be on Node >= 8.x and Yarn >= 1.5.
1. Clone guzzle-docs repository from github https://github.com/justanalytics/guzzle-docs
1. checkout the "master" branch of that repository (git checkout master)
1. `cd website`
1. `npm install`
1. `yarn start` (or npm start)


### Workflow of contributing a specific change in documentation

1. Contributor forks a branch from the master branch `git checkout -b <new_branch_name>`
1. Makes changes to existing markdown file(s) and/or adds new markdown files and tests them by running the documentation site locally using `yarn start`.
1. Commits the changes to the branch, pushes the branch and creates a pull-request to merge that branch into the `master` branch.



## Publishing 

### Publisher's environment setup

* The publisher (i.e. persons who should be allowed to publish changes to the documentation site), needs to do all the setup that is needed for Contributor's role.

* Additionally, the publisher should be allowed to push to the `master` branch of the repository.

* The publisher sets environment variable GIT_USER and sets it to his GitHub ID (not email address but just alphanumeric github ID).

* The Publisher reviews the pull-request and merges to `master` branch.

* Publisher updates his own local repository by doing a `git pull` and gets master branch which should have recently merged pull-requests which were accepted by the publisher.

* If the publisher himself is a contributor and wants to contribute a change, he may directly work on the master branch, commit and push the changes to the master branch. All steps related to creating a branch, raising a pull-request and merging pull request can be skipped. 


### Publishing from master branch

Publishing the current version of code in the `master` branch to the live documentation website. 


* Go to the guzzle-docs/website folder on the command prompt / terminal. 

* Execute the following command (assuming you have already set GIT_USER environment variable)

cmd /C "set CURRENT_BRANCH=master && set USE_SSH=true && yarn run publish-gh-pages"

The latest version of the website should be published within around a minute to the live website.


