# GDN Architecture Guidelines

## Introduction
This document is designed to provide a set of guidelines for contributors to architect new GlobalDeveloperNetwork features.  New 
contributors and developers who are unfamiliar with our architecture format should refer here before submitting pull requests.
We're pretty straight-forward with how we document our microservice architecture, but we also like to keep things consistent so 
please read on if you are interested in becoming a contributor.

## Who is this for?
All developers and contributors who are going to architect new features on the GDN open source projects, and who seek to document 
those features.

## Document Format
Each architecture document should contain:

- An Overview
- List of components and their short descriptions (1-2 paragraphs)
- Minimum Viable Product functionality expectations

### Diagrams

The following diagrams must be included in your architecture document:
 
| Type | Description |
|---|---|
| _Component Diagram_ | What are the system functions and how do they interact |
| _Physical Diagram_ | Where will the component be deployed |
| _Security Diagram_ | authc, authz, trust relationships, auditing as defined in [Security Architecture Standards](./security-architecture) |

### How do I make the diagrams?


##### Example:
![Component](https://www.plantuml.com/plantuml/svg/ZP4z3y8W48PtVyMbpaHc1rCTs5pis30WlHZI3mn7QupnlmisKLeJzPRZuytplWSvUULytpOBUDLPwLgT4BAzqSuIki5eX5qMhcw9x5bbcsZOKG8iEHU2yrHu_mdVPZFqbAlaY1LYAZeWsTvf99cSfsvlky9R5nV5bJosSpieE_GNwsf6eqvEyyVTzz53HCOsd--n1krGUQHLXGt6Rhh1raZ_uUQn0YzEWXHQe4P8ZbqLFl01)

<details><summary>Show UML Code</summary>
<p>
  
```
@startuml
    package "Microservice B"   {
       [microservice-b]  #00FF00
    }
    package "Microservice A" {
        [microservice-a] #00FFFF
        [Resources]
    }
    package "Storage System" {
        [network-storage]
    }

       
    [microservice-a] --> [microservice-b] : creates/deletes/invokes
    [microservice-a] --> [network-storage] : Stores State

   @enduml
```
</p>
</details>

##### Instructions:

1. Visit [PlantText](https://www.planttext.com/)
2. Write UML code
3. Embed SVG as `![Component](--SVG URL --)`

## Example Architecture Page
Here's a link to the [General Architecture](./general-architecture), to be used as an example of what we are after.

## Architecture approval process

Currently this process is loose at best, but essentially:
1. Submit a pull request with your architecture proposal to [any repo in our network](https://github.com/GlobalDeveloperNetwork)
2. Add two maintainers as reviewers
3. Both maintainer and member discussions occur
4. Profit?
