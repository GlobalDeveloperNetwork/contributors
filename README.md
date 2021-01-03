[![License](http://img.shields.io/badge/license-affero%20gpl%203.0-yellow)](https://choosealicense.com/licenses/agpl-3.0/)
[![Open Source Stacks](https://img.shields.io/badge/Open%20Source%20Stacks-blue)](https://www.opensourcestacks.com)
[![Groovy](https://img.shields.io/badge/language-Groovy-green)](https://github.com/apache/groovy)
[![Node.js](https://img.shields.io/badge/language-NodeJS-green)](https://npmjs.com)
[![12 Factor App](https://img.shields.io/badge/app-12--factor-yellow)](https://12factor.net/)


# GDN Contributors
A repository designed for contributors to the OpenSourceStacks.com project.  An initiative for providing a management interface for describing, building, and deploying different full stack strategies using open source software.

## What is this?
A repository for contributor guidelines and other contributor related information.  The Global Developer Network is a network of like-minded open source developers who are all seeking to participate creating definitions for the Full Stack Definition Language (FSDL) OSS project.  The language is actually a DSL (Domain Specific Language) that is highly specific to the Full Stack Strategy domain, i.e.- describing your stack technology and making sure it is fully functional, tested, and compliant with security controls. 

## How does it work?
The DSL provides an abstraction layer for applying stack transformations at build time. These same abstractions allow for the inspection (i.e.- headless browser testing), unit and integration testing of [Docker](https://hub.docker.com/) images, package management, CDN, and other 3rd party software or API dependencies you require to be compliant with specific standards in order to be deployed from a CICD pipeline or through `kubectl` (or systems like Rancher and the Rancher CLI).

## What do you mean by a "Stack Definition"?
A stack definition is a `.stack` file that is generated by a developer when creating their [Kubernetes-based](https://kubernetes.io/docs/home/) [Helm chart](https://helm.sh/docs/topics/charts/).  Helm is an open source provider of a Charting specification that simplifies deployment of K8s YAML by providing a `values.yaml` and `values.schema.json` file.  These values are simply filled out by a user and when deployed they are assembled along with the charts.  Our stack definition is created for build time operations, not deployment.  

## Why build time?
Our focus is on the declaration of immutable artifacts that are secured, and provide digital signatures for validation and verification using GPG.  We provide our offering separate from Helm via a CLI (Command Line Interface) that will ask you a series of questions, and through your answers deploy a `.stack` definition locally for local testing.  

## Testing the API
We provide an indivdual language module for each transformation or integration test, this allows for each module to be public and open source, while still providing the flexibility to run locally.  It also ensures the modules are versioned and immutable.  As you develop your `.stack` file, you can utilize examples that we provide and browse our documentation at [stackStandard.com](https://stackstandard.com).  

## Publishing to your Helm chart
Our CLI will update your existing Helm charts for conformance standards when tests succeed through our API.  You can optionally have our CLI add in your stack definition to the Helm chart itself as YAML declarations, but this is not required.  This can be highly useful for distributed applications that want to resell and conform to the FSDL.  It is also very useful for UI theme, and other types of distributions where the stack needs to be modified idempotently.  

## Idempotence and Language Support
Right now we are focusing on just one language: Javascript for Node.js stacks.  In the near future we will be establishing this FSDL and our Open API in a way that is language agnostic but supports multiple SDKs.

## FSDL Privacy
For some use cases where the stack has been modified to work with on-premise or private 3rd party software systems, it may be best to keep the stack definition private.  We adhere to a standard that provides both options.  See [StackStandard](https://stackstandard.com) for more details.  (Launching January 15th 2021)

# What does DSL describe?
The DSL is actually a querying meta-language that looks much like json, just with additional capabilites.  It is designed to make it as simple as possible to "ask" for a behavior based on a specific set of conditions and return a "result-as-code" (RAC) response.  The responses are stored as Docker containers that are digitally signed, and distributed using NPM as a generic loader that can be easily re-used as individual NPM modules. 

# Loading

## Example
```
$ cat test.bhv.stack | npx gsys publish behavior 
{
  "name": "@GlobalDeveloperNetwork/module",
  "description": "test-behavior",
  "version": "1.0.1",
  "author": "Full Stack Engine, LLC",
  "bin": {
    "gsys": "./bin/run load --with-tests=false ${CONDITION}"
  },
  "verifyKey": "------ PUBLIC KEY BLOCK --------",
  "supported": {
     "conditions": "onLogin, onLoadAuth",
     "languages": "javascript, scala",
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
