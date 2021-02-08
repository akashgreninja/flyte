![Flyte Logo](rsts/images/flyte_lockup_gradient_on_light.png "Flyte Logo")

[![Current Release](https://img.shields.io/github/release/lyft/flyte.svg)](https://github.com/lyft/flyte/releases/latest)
[![Build Status](https://travis-ci.org/lyft/flyte.svg?branch=master)](https://travis-ci.org/lyft/flyte)
[![License](https://img.shields.io/badge/LICENSE-Apache2.0-ff69b4.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)
![Commit activity](https://img.shields.io/github/commit-activity/w/lyft/flyte.svg?style=plastic)
![Commit since last release](https://img.shields.io/github/commits-since/lyft/flyte/latest.svg?style=plastic)
![GitHub milestones Completed](https://img.shields.io/github/milestones/closed/lyft/flyte?style=plastic)
![GitHub next milestone percentage](https://img.shields.io/github/milestones/progress-percent/lyft/flyte/11?style=plastic)
[![Docs](https://readthedocs.org/projects/flyte/badge/?version=latest&style=plastic)](https://flyte.rtfd.io)
![Twitter Follow](https://img.shields.io/twitter/follow/flyteorg?label=Follow&style=social)
[![Slack Status](https://img.shields.io/badge/slack-join_chat-white.svg?logo=slack&style=social)](https://forms.gle/UVuek9WfBoweiqcJA)

Flyte is a container-native, type-safe workflow and pipelines platform optimized for large scale processing and machine learning written in Golang. Workflows can be written in any language, with out of the box support for Python, Java and Scala.

# Homepage
- [flyte.org](https://flyte.org)
- [Docs](https://flyte.readthedocs.io/en/latest/)

# Introduction
Flyte is a fabric that connects disparate computation backends using a type safe data dependency graph. It records all changes to a pipeline, making it possible to rewind time. It also stores
a history of all executions and provides an intuitive UI, CLI and REST/gRPC API to interact with the computation.

Flyte is more than a workflow engine, it provides workflows as a core concepts, but it also provides a single unit of execution - tasks, as a top level concept. Multiple tasks arranged in a data
producer-consumer order creates a workflow. Flyte workflows are pure specification and can be created using any language. Every task can also by any language. We do provide first class support for
python, making it perfect for modern Machine Learning and Data processing pipelines.

# Resources
Resources that would help you get a better understanding of Flyte.

# Communication channels
- [Slack Org](https://forms.gle/UVuek9WfBoweiqcJA)
- [Email list](https://groups.google.com/a/flyte.org/g/users)

# Biweekly Community Sync
- Starting April 21 2020, the Flyte community meets every other Tuesday at 9:00 AM PST (US West coast time).
- You can join the [zoom link]( https://us04web.zoom.us/j/71298741279?pwd=TDR1RUppQmxGaDRFdzBOa2lHN1dsZz09).
- Meeting notes are captured in [Doc](https://docs.google.com/document/d/1Jb6eOPOzvTaHjtPEVy7OR2O5qK1MhEs3vv56DX2dacM/edit#heading=h.c5ha25xc546e)
- Demo Signup [Sheet](https://docs.google.com/spreadsheets/d/1Bz-s3SpMm1hGl6Z5y3HcxrNBcg9ZhSgqVgmCxK_eEhs/edit#gid=0)

## Conference Talks
- Kubecon 2019 - Flyte: Cloud Native Machine Learning and Data Processing Platform [video](https://www.youtube.com/watch?v=KdUJGSP1h9U) | [deck](https://kccncna19.sched.com/event/UaYY/flyte-cloud-native-machine-learning-data-processing-platform-ketan-umare-haytham-abuelfutuh-lyft)
- Kubecon 2019 - Running LargeScale Stateful workloads on Kubernetes at Lyft [video](https://www.youtube.com/watch?v=ECeVQoble0g)
- re:invent 2019 - Implementing ML workflows with Kubernetes and Amazon Sagemaker  [video](https://youtu.be/G-wzIQQJKaE)
- Cloud-native machine learning at Lyft with AWS Batch and Amazon EKS [video](https://youtu.be/n_rRb8u1GSM)
- OSS + ELC NA 2020 [splash](https://ossna2020.sched.com/event/313cec91aa38a430a25f9571039874b8)
- Datacouncil [splash](https://docs.google.com/document/d/1ZsCDOZ5ZJBPWzCNc45FhNtYQOxYHz0PAu9lrtDVnUpw/edit)

## Blog Posts
 1. [Introducing Flyte: A Cloud Native Machine Learning and Data Processing Platform](https://eng.lyft.com/introducing-flyte-cloud-native-machine-learning-and-data-processing-platform-fb2bb3046a59)

## Podcasts
- TWIML&AI -  [Scalable and Maintainable ML Workflows at Lyft - Flyte](https://twimlai.com/twiml-talk-343-scalable-and-maintainable-workflows-at-lyft-with-flyte-w-haytham-abuelfutuh-and-ketan-umare/)
- Software Engineering Daily - [Flyte: Lyft Data Processing Platform](https://softwareengineeringdaily.com/2020/03/12/flyte-lyft-data-processing-platform-with-allyson-gale-and-ketan-umare/)


# Features
 - Used at Scale in production by 500+ users at Lyft with more than *900k* workflow executed a month and more than *30+* million container executions per month
 - Fast registration - from local to remote in one second.
 - Centralized Inventory of Tasks, Workflows and Executions
 - Single Task Execution support - Start executing a task and then convert it to a workflow
 - gRPC / REST interface to define and executes tasks and workflows
 - Type safe construction of pipelines, each task has an interface which is characterized by its input and outputs. Thus illegal construction of pipelines fails during declaration rather than at
   runtime
 - Types that help in creating machine learning and data processing pipelines like - Blobs (images, arbitrary files), Directories, Schema (columnar structured data), collections, maps etc
 - Memoization and Lineage tracking
 - Workflows features
  * Multiple Schedules for every workflow
  * Parallel step execution
  * Extensible Backend to add customized plugin experiences (with simplified User experiences)
  * Arbitrary container execution
  * Branching
  * Inline Subworkflows (a workflow can be embeded within one node of the top level workflow)
  * Distributed Remote Child workflows (a remote workflow can be triggered and statically verified at compile time)
  * Array Tasks (map some function over a large dataset, controlled execution of 1000's of containers)
  * Dynamic Workflow creation and execution - with runtime type safety
  * Container side plugins with first class support in python
  * PreAlpha: Arbitrary flytekit less containers supported (RawContainer)
 - Maintain an inventory of tasks and workflows
 - Record history of all executions and executions (as long as they follow convention) are completely repeatable
 - Multi Cloud support (AWS, GCP and others)
 - Extensible core
 - Modularized
 - Automated notifications to Slack, Email, Pagerduty
 - Deep observability
 - Multi K8s cluster support
 - Comes with many system supported out of the box on K8s like Spark etc.
 - Snappy Console
 - Python CLI
 - Written in Golang and optimized for performance of large running jobs

## In Progress
 - Golang CLI - flytectl

## Coming Soon
 - Reactive pipelines
 - Grafana templates (user/system observability)
 - More integrations

# Available Plugins
 - Containers
 - K8s Pods
 - AWS Batch Arrays
 - K8s Pod arrays
 - K8s Spark (native pyspark and java/scala)
 - Qubole Hive
 - Presto Queries
 - Distributed Pytorch (K8s Native) - Pytorch Operator
 - Sagemaker (builtin algorithms & custom models)
 - Distributed Tensorflow (K8s Native) - TFOperator
 - Papermill Notebook execution (python and spark)

## Coming soon
 - Flink-K8s

# Current Usage 
- [Freenome](https://www.freenome.com/)
- [Lyft Rideshare, Mapping](https://www.lyft.com/)
- [Lyft L5 autonomous](https://self-driving.lyft.com/level5/)
- [Spotify](https://www.spotify.com/)

# Changelogs
[Changelogs](CHANGELOG/README.md)


# Component Repos 
Repo | Language | Purpose | Status
--- | --- | --- | ---
[flyte](https://github.com/lyft/flyte) | Kustomize,RST | deployment, documentation, issues | Production-grade
[flyteidl](https://github.com/lyft/flyteidl) | Protobuf | interface definitions | Production-grade
[flytepropeller](https://github.com/lyft/flytepropeller) | Go | execution engine | Production-grade
[flyteadmin](https://github.com/lyft/flyteadmin) | Go | control plane | Production-grade
[flytekit](https://github.com/lyft/flytekit) | Python | python SDK and tools | Production-grade
[flyteconsole](https://github.com/lyft/flyteconsole) | Typescript | admin console | Production-grade
[datacatalog](https://github.com/lyft/datacatalog) | Go  | manage input & output artifacts | Production-grade
[flyteplugins](https://github.com/lyft/flyteplugins) | Go  | flyte plugins | Production-grade
[flytestdlib](https://github.com/lyft/flytestdlib) |  Go | standard library | Production-grade
[flytesnacks](https://github.com/lyft/flytesnacks) | Python | examples, tips, and tricks | Incubating
[flytekit-java](https://github.com/spotify/flytekit-java) | Java/Scala | Java & scala SDK for authoring Flyte workflows | Incubating
[flytectl](https://github.com/lyft/flytectl) | Go | A standalone Flyte CLI | Incomplete


# Production K8s Operators

Repo | Language | Purpose
--- | --- | ---
[Spark](https://github.com/GoogleCloudPlatform/spark-on-k8s-operator) | Go | Apache Spark batch
[Flink](https://github.com/lyft/flinkk8soperator) | Go | Apache Flink streaming

# Top Contributors
Thank you to the community for making Flyte possible.
 - [@wild-endeavor](https://github.com/wild-endeavor)
 - [@katrogan](https://github.com/katrogan)
 - [@EngHabu](https://github.com/EngHabu)
 - [@akhurana001](https://github.com/akhurana001)
 - [@anandswaminathan](https://github.com/anandswaminathan)
 - [@kanterov](https://github.com/kanterov)
 - [@honnix](https://github.com/honnix)
 - [@jeevb](https://github.com/jeevb)
 - [@jonathanburns](https://github.com/jonathanburns)
 - [@migueltol22](https://github.com/migueltol22)
 - [@varshaparthay](https://github.com/varshaparthay)
 - [@pingsutw](https://github.com/pingsutw)
 - [@narape](https://github.com/narape)
 - [@lu4nm3](https://github.com/lu4nm3)
 - [@bnsblue](https://github.com/bnsblue)
 - [@RubenBarragan](https://github.com/RubenBarragan)
 - [@schottra](https://github.com/schottra)
 - [@evalsocket](https://github.com/evalsocket)
 - [@matthewphsmith](https://github.com/matthewphsmith)
 - [@slai](https://github.com/slai)
 - [@derwiki](https://github.com/derwiki)
 - [@tnsetting](https://github.com/tnsetting)
 - [@jbrambleDC](https://github.com/jbrambleDC)
 - [@igorvalko](https://github.com/igorvalko)
 - [@chanadian](https://github.com/chanadian)
 - [@surindersinghp](https://github.com/surindersinghp)
 - [@vsbus](https://github.com/vsbus)
 - [@catalinii](https://github.com/catalinii)
 - [@kumare3](https://github.com/kumare3)


