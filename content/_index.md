---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
  - block: markdown
    content:
      title: '📚 Tech Stack'
      subtitle: ''
      text: |-
        I am a versatile engineer with extensive experience in backend development, data engineering, and infrastructure management. My tech stack reflects my expertise in various technologies and tools that ensure efficient, scalable, and reliable systems. Here's a detailed overview of my chosen tech stack:
        
        **Data Engineering**
        - Batch Pipeline: Spark, Airflow, dbt
        - Streaming Pipeline: Kafka, Flink
        - File Format: Parquet, Protobuf, Thrift
        - Table Format: Delta Lake, Iceberg, Hudi
        - Query Engine: Trino, BigQuery

        **Backend Engineering**
        - Language: Python, Go, Java, Node.js
        - API: REST, gRPC
        - Database: PostgreSQL, MongoDB
        - Search Engine: Elasticsearch
        - Cache: Redis
        - Services Communication: Kafka, RabbitMQ

        **Infrastructure**
        - Cloud Platform: AWS, GCP
        - Container: Docker, Kubernetes
        - IaaC: Terraform, Ansible
        - CICD: Github Action, Gitlab CI
        
        Please reach out to collaborate 😃
  - block: collection
    id: projects
    content:
      title: Recent Projects
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 3

  - block: collection
    id: blogs
    content:
      title: Recent Articles
      subtitle: ''
      text: ''
      count: 3
      filters:
        folders:
          - blogs
    design:
      view: date-title-summary

---
