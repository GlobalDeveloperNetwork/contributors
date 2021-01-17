[![License](http://img.shields.io/badge/license-affero%20gpl%203.0-yellow)](https://choosealicense.com/licenses/agpl-3.0/)
[![Open Source Stacks](https://img.shields.io/badge/Open%20Source%20Stacks-blue)](https://www.opensourcestacks.com)
[![Groovy](https://img.shields.io/badge/language-Groovy-green)](https://github.com/apache/groovy)
[![Node.js](https://img.shields.io/badge/language-NodeJS-green)](https://npmjs.com)
[![12 Factor App](https://img.shields.io/badge/app-12--factor-yellow)](https://12factor.net/)

> Important!  Much of the functionality described in this document is in VERY active development on our Gitlab instance.  Please fill out this form for contributor-level access to it.  If you inhtend on using any code you find published to Github, expect that it will NOT be functional until our alpha version for early adopters of the language is released.   (Mid Feb 2021)

# GDN Contributor Information
Welcome to the Global Developer Network 501(c)(6) pending collective, open source project.  Built by code contributions from open source developers world-wide.
We intend to accept contributions once our non-profit paperwork is officially approved, and 100% will go towards funding this development effort.
We already have some corporate sponsorship, but are always looking for more backers.

# What are we doing?
We are re-inventing the development process for Full Stack applications with an emphasis on business requirements, domain driven operations, security-first specifications with conformance to industry-standard best practices, and test coverage.  Just ask us!

# Discord Community
Please join us on [GDN Discord chat](https://discord.gg/r5vXHwgb).

## GDN Repo for Contributors
A repository designed for contributors to the [OpenSourceStacks.com](https://fullstack.llc) project, an initiative for providing a management interface for describing, building, and deploying different full stack strategies using open source software.  It will provide freelance gigs for open sourcers while connecting them directly to clients, and will  use a structured but enjoyable method for the onboarding process, virtual workforce solutions, and business process oversight to augment the experience via the [Full Stack Engine](https://fullstack.llc).

## What is this?
A repository for contributor guidelines and other contributor related information.   This repository will also contain a branch for the fully transparent open source [StackStandard.com](https://stackstandard.com) registry, which provides a taxonomy of behaviors from which [developers of packages and themes](https://www.notion.so/investhere/2-StackStandard-com-2563664485504dd9860d53a270df8631#78a9826a8a3740f6a7474f2d052a2ff3) may adopt conformance, and adopt usage of security control specifications for which we provide testing.   Should you choose to be an early adopter, you will get a fancy badge for your website that says you adhere to these specific standards.  We have a great process for validating the tests and presenting the status of your organization, and we will be marketing early adopters in our future campaigns.

## Early adoption of the language 
#### (Phase 1)

GDN provides an open collective network of like-minded developers who are all seeking to participate in creating definitions for the Fullstack Domain Specific Language (FDSL) project.  The language is actually a superset of GraphQL and can be used that way.   It will also come in a short form notation style language that looks very similar to a DSL (Domain Specific Language) and is highly specific to the Full Stack Strategy domain.   (i.e.- describing your stack technology and making sure it is fully functional, tested, and compliant with security controls.)

## How does it work?
The FDSL provides an abstraction layer for applying `stack actions` at `build time`, and it does this through packages on NPM that are run as docker containers using our CLI. The CLI user does *not* need to worry about Docker or containers, as they are built intrinsically into CLI code.  These `stack actions` running as `containers` perform as compilable tasks on your stack, including API calls, Transformations from RAC (results as code), introspection of packages (RASCI/ Results As Secure Code Introspection), attachment of telemetry for stack tracing (Event Listeners), and Fluentd Logging collectors (for attaching streaming logs to Kubernetes) on the stack.  We are using [Terraform](https://www.terraform.io/) for some actions, and if you use our cloud, [Vault](https://www.vaultproject.io/) for secrets management controls (otherwise K8s Secrets).  

### Testing
These same abstractions allow for the inspection (Selenium UAT), unit and internal integration testing of [Docker](https://hub.docker.com/) images, package management, CDN, and other 3rd party software or API dependencies required to be compliant with specific standards in order to be deployed from a CICD pipeline or through `kubectl`.  All a package maintainer needs in order to adopt this standard is our CLI tool, which is pluggable and modular, in order to create the `.stack` definition format and publish it to NPM via Git along with a [HELM3](https://helm.sh/docs/topics/charts/) chart of your stack.  This is done automatically for multiple packages using the `monorepo` pattern [described here](https://github.com/GlobalDeveloperNetwork/contributors#loading-your-repo).

> Since a Helm3 chart obviously needs to be created for each backend, we will [provide consulting](https://discord.gg/r5vXHwgb) for various backends until we have a CLI plugin for creating them.  We are supporting the following configurations from our first Generally Available (GA) status:  

Google, Microsoft, and Amazon clouds for GraphQL APIs:

* Postgres with a Hasura Layer, providing the GraphQL API
* Postgres with an Express or Fastify GraphQL API
* Postgres with a NestJS layer and GraphQL API
* MongoDB with  an Express or Fastify GraphQL API
* Firestore with a GraphQL API (firestore-apollo)
* Cosmos DB with a GraphQL API (using Hasura and the Postgres driver)
* DocumentDB or DynamoDB with a GraphQL API (using AWS AppSync and Lambda, or DynamoDB configurations)
* Socketclusters.io for streaming listener events.
* Meili search nodes are also supported for those looking to implement realtime search in their cluster.

### Out of the box
We provide the following functions out of the box:
- GitOps strategy - i.e.- we abstract away k8s and make it simple to use for developers who don't have a PhD. in clusterology.
- We provide a comprehensive, recursive installation method as post-install hooks so theme and other developers with many packages can publish easily to our system using one repo and by not having to modify all of their packages in egregious ways.
- All code is built using our CLI (`npx gsys` for no global-conflicts one-time-dependency installs) 
- All code is tested using local integration tests and the ability to use Gitlab AutoDevOps or Github actions, while still providing test coverage to StackStandard.com.
- All builds are triggered by a condition, action, and event chain that is langage agnostic, pub/sub socket stream-ready, and provides Vault support for runtime secrets.
- Because we provide hosted Vault integration, you can distribute your app using Content Trust on the images and our CLI will store them on a secure Quay repo we maintain.
- If you need digital asset protection, you can choose to encrypt your assets during S3 cold storage.
- Our StackStandard documentation will explain all of our MVP security configurations, [offerings](https://app.getguru.com/card/c86b5pji/What-security-offers-are-going-to-definitely-be-provided-by-the-StackStandardcom-MVP), and more.

## What do you mean by a "Stack Definition"?
A stack definition is a `.stack` file that is generated by a developer when creating their [Kubernetes-based](https://kubernetes.io/docs/home/) [Helm chart](https://helm.sh/docs/topics/charts/).  Helm is an open source provider of a charting specification that simplifies deployment of K8s YAML by providing a `values.yaml` and `values.schema.json` file.  These values are simply filled out by a user and when deployed they are assembled along with the charts.  Our stack definition is created for build time operations, not deployment/ runtime.  That being said, we still are supporting running build time integration tests via popular CICD.  This is achieved by providing simple webhooks through endpoints that can trigger CICD jobs on our servers.  Each version pushed to us is immutable and tree-checksums are validated along with DCT, and potentially Notary trust delegations (in the future).  So it is trivial to support the use case of external CICD triggers so long as we can validate the chain of trust requesting it.

## Build time Ops
Our focus is on the declaration of immutable artifacts that are secured, and provide digital signatures for validation and verification using GPG.  We provide our offering separate from Helm via a CLI (Command Line Interface) that will ask you a series of initialization questions, and through your answers deploy a `.stack` definition locally for local testing.  

## Testing the API
We provide an indivdual language module for each transformation or integration test, this allows for each module to be public and open source in any language (that supports Git workflows), while still providing the flexibility to run locally.  It also ensures that modules are versioned and immutable.  As you develop your `.stack` file, you can utilize interactive examples that we provide and browse our documentation at [stackStandard.com](https://stackstandard.com) (will be launched by Feb 15th 2021).  

## Publishing to your Helm chart
Our CLI will update your existing SSI with conformance standards when tests succeed through our API.  You can optionally have our CLI add in your stack definition to the Helm chart itself as YAML declarations, but this is not required.  This can be highly useful for distributed applications that want to resell and conform to the FSDL.  It is also very useful for UI theme, and other types of distributions where the stack needs to be modified idempotently.  

## Idempotence and Language Support
Right now we are focusing early adoption of just one language: ES6+ for Node.js stacks.  In the near future we will be establishing this FSDL in a way that is language agnostic and supports multiple SDKs.  We've planned for it, we just can't execute with at least 100 early adopters for each language.

## FSDL Privacy
For some use cases where the stack has been modified to work with on-premise or private 3rd party software systems, it may be best to keep the stack definition private.  We adhere to a standard that provides both options.  See [StackStandard](https://stackstandard.com) for more details.  (Launching January 15th 2021)

# What does DSL describe?
The DSL is actually a querying meta-language that looks much like javascript and/or string literals, just with additional capabilites.  It is designed to make it as simple as possible to "ask" for a behavior based on a specific set of conditions and return a "result-as-code" (RAC) response.  The responses are stored as Docker containers that are digitally signed, and distributed using NPM as a generic loader that can be easily re-used as individual NPM modules.   This allows you to run everythign locally, and at CICD time, with the added benefit of 3rd party auditing (our service) whenever CICD builds are triggered.

# Loading your repo

## Example Monorepo for Authors of multiple packages that want to use the Gitops.Systems (Gsys) and Fullstack DSL (FDSL) for CICD workflows (i.e.- Gitlab AutoDevOps or Github Actions):
```bash
$ / package.json
{
    "install:verify": "cd projects/verification && npx yarn-recursive",                       // runs tooling package build for encryption and docker manipulation
    "install:cli-all": "cd projects/cli-all && npx yarn-recursive",                           // runs yarn to build via npx the CLI and all supported plugins         
    "install:PKG": "cd projects/PKG && npx yarn-recursive && \
                    ln -s ./PKG ___INSTALL_YOUR_PACKAGES_HERE && \
                    npx @fdsl/verify",                                                        // verify all of your own supported packages 
    "postinstall": "npx yarn gsys && ln -s ./.bin/gsys gsys; gsys verify --recursive"         // run verification from the gsys CLI
}
```
## Building a Monorepo:
```bash
   npx yarn-run-all
```

## Example package contained in the directory of your choice:
```bash

$ cat package.json | npx gsys publish behavior 
{
  "name": "@GlobalDeveloperNetwork/module",
  "description": "test-behavior",
  "version": "1.0.1",
  "author": "Full Stack Engine, LLC",
  "bin": {
    "gsys": "./bin/run load --with-tests=false ${CONDITION}"
  },
  "devDependencies": {
     "@gsys/loader": "^1.5.9",
     "gsys": "^1.1.0"",
     "dockerode": "^3.2.1"
  }
}
```

All results are digitally signed and encrypted by DCT using a private and public key pair that can verify author authenticity.
The docker images can be [created by Node](https://www.npmjs.com/package/dockerode), since this is the first language we are focusing on support for.

--- 

Some portions of this repo are from the [CrateKube project](https://github.com/cratekube/cratekube), i.e.- the architectural standards, which is now deprecated by Cisco.  

```bash
The code is deprecated and non-licensed, so we are resurrecting some portions of the project for our CLI.  
This has been checked by our legal team and we are compliant with all applicable laws.
```

© 2021 Copyright Full Stack Engine by LARGE Holdings Ltd. dba Large Marketing Group, LLC.  

___
> Questions or concerns about content provided by our service?  We are DMCA compliant, so if you do have questions that need to be addressed, please contact our [legal](mailto:legal@large.marketing) staff directly.
