# Tapis Project

## Mentors

[Joe Stubbs](https://github.com/joestubbs/)

[Smruti Padhy](https://github.com/smpadhy)


## Project Ideas

###  Automated Reasoning Interfaces For Tapis Security Policies

#### Abstract
As the number of users of a cloud system grows, reasoning about the set of access control policies governing their resources becomes increasingly difficult. Tools from Formal Methods, such as Satisfiability Modulo Theories (SMT) [1], provide techniques for automatically reasoning about entire collections of policies, but using these tools requires expertise. This project will build upon the CloudSec library and the Tapis API framework to develop an HTTP RESTful API and graphical interface for analyzing entire sets of Tapis security policies by nonexperts. 

| **Intensity**                          | **Priority**              | **Involves**  | **Mentors**              |
| -------------                          | ------------              | ------------- | -----------              |
| {{ Easy to Moderate }} | {{ Medium }} | {{ Developing new REST API and GUI interface to tools for analyzing Tapis security policies }}         | {{ [Joe Stubbs](https://github.com/joestubbs/)  [Smruti Padhy](https://github.com/smpadhy)  }} |

#### Technical Details

The Tapis project provides web-based APIs enabling researchers to automate data management and computational tasks on cloud, high-throughput and HPC resources. Tapis uses a fine-grained permissions model that allows users to manage who can access their datasets and research codes. Often times, large projects (such as DesignSafe) will create a mixture of community resources (e.g., public datasets, public applications, etc.) as well as resources private to individual investigators or research labs. As users join and leave the community, Tapis permissions must evolve. Over time, large projects accumulate tens of thousands of permissions in Tapis. How can we be sure that the permissions are correct? In general, we would like to be able to check that these permissions conform to certain rules. For example, we might like to know that all users have modify access to their home directories on all HPC systems, and they have read-only access to published datasets, while only certain administrative users can add new files to the published data collection. With SMT, we can programmatically prove or disprove such statements, but using these libraries requires background and expertise in formal methods. 

We have developed a Python library, CloudSec ([2, 3]), that provides an extensible, high-level Python interface for building policy specifications and formally reasoning about policy sets without any knowledge of SMT. CloudSec’s backend uses different SMT solvers, such as Z3 or CVC5, to prove statements about policies or find counterexamples. CloudSec also integrates third-party sources of policy information, such as Tapis security policies, through its Connectors abstraction. 

This project will build upon the CloudSec library to develop a RESTful HTTP API for reasoning about Tapis policies. The HTTP API must be able to serialize and deserialize inputs to and results from the CloudSec core package, including the p_imp_q() function and the ImplResult class. It must also deal with other technical issues, such as options for running multiple solvers in parallel (already provided by the CloudSec library) and handling timeouts. The project will provide an OpenAPI specification for the HTTP API so that clients in various languages (e.g., Python, TypeScript) can be generated automatically. We will work with standard Python tools for API development, including FastAPI, jsonschema, and Uvicorn, Docker for containerization, and Python libraries for interacting with Tapis (e.g., the Tapipy library). 

Finally, this project will develop a graphical interface to allow users to check Tapis policies against specifications they define in a web browser. The front-end will be embedded in the Tapis UI project [4] using the Tapis TypeScript library [5]. This part will involve updating the sidebar for the new panel, adding a service-level routers and layout, creating models for each endpoint to be exposed, and adding links to the service from the existing UI. Providing a graphical interface to the tool and API will allow it to be used by a wider audience. 



#### Helpful Experience

* Working knowledge of Python and TypeScript 
* Familiarity with cloud and HTTP/RESTful APIs and technologies
* Familiarity with cloud security policies, including role-based access controls (RBAC)


#### First steps

* Read about the Tapis project [6] 
* Read our paper on CloudSec [3]
* Become familiar with API development in Python, for example, using FastAPI
* Become familiar with OpenAPI specifications [7]

#### Benefits of working on this project

Students working on this project will develop skills in the following areas:
* Modern, state-of-the-art SMT solvers, including Z3 and CVC5.
* Web service development in Python and associated technologies, e.g., RESTful design, OpenAPI definitions, language SDK generation, etc. 
* Front-end development in TypeScript, React and related technologies

#### References
[1] A. R. Bradley and Z. Manna. The Calculus of Computation: Decision Procedures with Applications to Verification. Springer, 2017.

[2] CloudSec GitHub Repository. https://github.com/applyfmsec/cloudsec

[3] CloudSec: An Extensible Automated Reasoning Framework for Cloud Security Policies. https://arxiv.org/pdf/2307.05745.pdf

[4] Tapis UI GitHub Repository. https://github.com/tapis-project/tapis-ui/

[5] Tapis TypeScript GitHub Repository. https://github.com/tapis-project/tapis-typescript

[6] Tapis Documentation. https://tapis.readthedocs.io/en/latest/

[7] OpenAPI Specification. https://swagger.io/specification/

