---
title: 'Building Machine Learning Pipelines'
date: 2024-08-01
---

Companies are spending billions on machine learning projects, but it’s money wasted if the models can’t be deployed effectively. In this practical guide, Hannes Hapke and Catherine Nelson walk you through the steps of automating a machine learning pipeline using the TensorFlow ecosystem. You’ll learn the techniques and tools that will cut deployment time from days to minutes, so that you can focus on developing new models rather than maintaining legacy systems.
Data scientists, machine learning engineers, and DevOps engineers will discover how to go beyond model development to successfully productize their data science projects, while managers will better understand the role they play in helping to accelerate these projects.

- Understand the steps to build a machine learning pipeline
- Build your pipeline using components from TensorFlow Extended
- Orchestrate your machine learning pipeline with Apache Beam, Apache Airflow, and Kubeflow Pipelines
- Work with data using TensorFlow Data Validation and TensorFlow Transform
- Analyze a model in detail using TensorFlow Model Analysis
- Examine fairness and bias in your model performance
- Deploy models with TensorFlow Serving or TensorFlow Lite for mobile devices
- Learn privacy-preserving machine learning techniques

My Comments:
- The title is a bit mislead, it should be clearer: "Building Machine Learning Pipelines with TENSORFLOW"
- Apache Beam is dead
  - https://www.reddit.com/r/dataengineering/comments/1916jyx/will_apache_beam_die_out/
  - there is no reason to learn beam unless you’re working at Spotify
  - My main beef with Beam is the huge difference in feature and bug between runners. Many examples in the documentation in the homepage fail to run on any runners but GCP Dataflow.
  - I'm not a huge fan of its syntax.




