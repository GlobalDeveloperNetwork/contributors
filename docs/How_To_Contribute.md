# GDN Contribution guidelines overview

We aim to make becoming a GlobalDeveloperNetwork contributor a simple and easy process. The following guidelines help to get you up and running with GlobalDeveloperNetwork contributions as quickly as possible.

## Contribution process

At a high level, the contribution process takes the following steps:

1. Choose an issue to work on.
2. Fork the repository containing the project you'd like to contribute to.
3. Develop the feature or fix the bug you've chosen to work on. Be sure to include tests.
4. Update the documentation, including the repository's README.md, as necessary.
5. Ensure that tests are passing and the project builds.
6. Open a pull request with your changes against master. Review our (pull request) PR creation guidelines below for more information.
7. Wait for reviewers. You will likely need to make some changes after the code review.
8. Once the reviews pass, we will merge your pull request.

## Local Development

Each repository includes a README that will provide instructions on how to build and run the code locally.

## Feature Requests and Bugs

Search our existing issues for feature requests and bugs. If one doesn't already exist for your feature or bug, create a new one. Issue templates are available to help guide you through this process.

## Contact

Reach out to us through comms@large.marketing to ask for help or provide feedback.


# Pull request (PR) guidelines

The following pull request guidelines service to walk users through the process of creating and submitting a
PR against a GlobalDeveloperNetwork repository. On the GlobalDeveloperNetwork team, we use the [forking strategy](https://gist.github.com/Chaser324/ce0505fbed06b947d962)
to manage changes. As a result, PRs are required to contribute code to our repositories.

## Creating a PR
To create a PR, use the following steps:
- Fork the repository you would like to contribute to
- Create a branch in your fork for your contribution
- Apply changes to your branch including test updates and documentation changes
- Create a PR from your branch to the target upstream branch using the GitHub UI

After the PR has been submitted, GlobalDeveloperNetwork maintainers will review the contribution according to our review process detailed below
and discuss the code with the contributor. After the review has completed, a GlobalDeveloperNetwork maintainer will merge the code into the project.

### Agree to the Developer Certificate of Origin
To avoid copyright issues with this open source project, all contributors *must* agree to the Developer Certificate of Origin (DCO)
vesion 1.1 for all contributions.  To confirm that you agree to the DCO, all commits must contain a Signed-off-by line with an
email matching the email from the commit.  For reference, the text below is version 1.1 of the
[Developer Certificate of Origin](https://developercertificate.org/)
```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.
1 Letterman Drive
Suite D4700
San Francisco, CA, 94129

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.


Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

### Git setup
If not configured globally, please configure your commits to provide a username and email:
```
git config user.name '<first name> <last name>'
git config user.email '<email address>'
```

To signoff contributions add the `-s/--signoff` option when committing to your branch:
```
git commit -s
## or
git commit --signoff
```

If you are using IntelliJ to commit your changes, be sure to check the Sign-off Commit box in the Commit Changes dialog. 

### PR best practices
For GlobalDeveloperNetwork projects, we use the following best practices for submitting PRs:
- avoid including unrelated commits
- avoid large changes unless absolutely required
- rebase your branch before submitting
    - squash your commits down to a single commit as part of the rebase ([rebase squashing guide](https://medium.com/@slamflipstrom/a-beginners-guide-to-squashing-commits-with-git-rebase-8185cf6e62ec))
- include test cases for any source code changes
  - we uses the [ava testing framework](https://github.com/avajs/ava) for node.js development
  - we use the [Spock](http://spockframework.org/spock/docs/1.3/index.html) testing framework for our Groovy microservices
  - we recommend using Test Driven Development (TDD), writing your tests first and coding the solution to the tests
- include documentation for changes that affect application contracts

Additionally, when submitting PRs please provide a title that accurately describes the change. If the PR fixes an issue be sure
to reference the issue number in the PR description. Keywords and syntax formatting for issue linking can be found
in the GitHub [documentation](https://help.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword).

### Specifying issue references
All commits and PRs should link to the original issue being resolved. In order to achieve that, follow the following syntax during commits and PRs:
- Each commit should begin with: `GlobalDeveloperNetwork/<repo_name>#<issue_number>`.
- The same reference, i.e., `GlobalDeveloperNetwork/<repo_name>#<issue_number>` should be added as a comment while creating a PR. 


### Code Review
Code review is an important part of our quality control process. As a result, all PRs must go through a review by GlobalDeveloperNetwork
maintainers. After a PR is submitted, one or more reviewers will be assigned to inspect the contribution. Each of the assigned
reviewers will either approve the submission or request changes. Once all requested changes have been addressed, the PR will
be merged by one of the assigned reviewers.

Our repositories [GitLab](https://docs.gitlab.com/ee/ci/) for private projects and [CircleCI](https://circleci.com/docs/) for public ones, please review the documentation
to understand how the CCI system applicable to you works.  Status checks on each repository ensure that changes cannot be merged until both the code review and automated build have
completed successfully.

To avoid a large backlog of stale PRs we have automation to close requests that have no activity after 2 weeks.  
Please make sure to review feedback and engage with our reviewers to get your contribution merged.

### Definition of Done
The GlobalDeveloperNetwork development team uses the following checklist to know when a contribution should be considered 'Done'. Each contribution *must*:
- Include a clear description and/or illustration explaining the relevancy of the contribution
- Contain working and clean code that is commented where needed
- Contain passing automated tests that cover the added functionality
- Be reviewed by at least two GlobalDeveloperNetwork maintainers
