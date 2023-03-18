#DataEngineering #Cloud #GCP 
# Big Data and Machine Learning on Google Cloud
Some learning path that maybe going to be useful:
- [Google Cloud Training](https://cloud.google.com/training)
- [Learning Path: Data Engineering and Smart Analytics](https://cloud.google.com/training/data-engineering-and-analytics)
- [Learning Path: ML and AI](https://cloud.google.com/training/machinelearning-ai)
## Google Cloud infrastructure
![[GCP Infra.excalidraw|700x300]]
## Product Categories
![[GCP Product Categories .excalidraw|700x300]]
## Data Engineering for Streaming Data
*Pub/Sub* is a distributed messaging service that can receive event messages from streams and publish them to subscribers. It ensures *at-least-once delivery*.  Pub/Sub has several capabilities:
- No provisioning is required
- APIs are open
- Global by default.
- Offers end-to-end encryption.

Moreover, Pub/Sub has three essential functions: *read, store, and broadcast*.  Publishers can send messages with a specific topic. A topic can be sent from many publishers and received by many subscribers. So we need a pipeline that can match Pub/Sub's scale. A popular solution for pipeline design is *Apache Beam*. It is a unified programming model to define and execute data processing pipelines, including ETL, batch, and stream processing.
```ad-question
title: Challenges related when coding the pipeline
- Will the pipeline code be compatible with both batch and streaming data, or will it need to be refactored?
- Will the pipeline code SDK have all the transformations, mid-flight aggregations, and windowing?
- Will the pipeline code SDK be able to handle later data?
- Are there existing templates or solutions that should be referenced?

```
*Dataflow* is a fully managed service for executing Apache Beam pipelines within the Google Cloud ecosystem. Dataflow is serverless and NoOps, using Dataflow means you can spend more time analyzing your datasets and less time provisioning resources to ensure your pipeline will succeed.
```ad-question
title: Questions when choosing an execution engine
- How much maintenance overhead is involved?
- is the infrastructure reliable?
- How is the pipeline scaling handled?
- How can the pipeline be monitored?
- Is the pipeline locked in to a specific service provider?
```
Tasks Dataflow performs when a job is received:
- Graph optimization $\rightarrow$ 
- Work scheduler
- Auto-scaler
- Auto-healing
- Work rebalancing
- Compute & Storage