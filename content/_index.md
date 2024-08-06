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
        - Batch Pipeline: Apache Spark, Apache Airflow, dbt
        - Streaming Pipeline: Apache Kafka, Apache Flink
        - File Format: Apache Parquet, Protobuf
        - Table Format: Delta Lake, Apache Iceberg
        - Query Engine: Trino, BigQuery

        **Backend Engineering**
        - Language: Python, Go, Java, Node.js
        - API: REST, gRPC
        - Database: PostgreSQL, MongoDB
        - Search Engine: Elasticsearch
        - Services Communication: Apache Kafka, RabbitMQ

        **Infrastructure**
        - IaaC: Terraform, Ansible
        - Container: Docker, Kubernetes
        - CICD: Github Action, Gitlab CI
        - Cloud Platform: AWS, GCP
        
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
