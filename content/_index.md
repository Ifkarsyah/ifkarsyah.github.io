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
        - Batch Pipeline: [Apache Spark](courses/spark), [Apache Airflow](courses/airflow), dbt
        - Streaming Pipeline: [Apache Kafka](courses/kafka), [Apache Flink](courses/flink)
        - File Format: [Apache Parquet](courses/parquet), Protobuf, Thrift
        - Table Format: [Delta Lake](courses/deltalake), [Apache Iceberg](courses/iceberg)
        - Query Engine: Trino, [BigQuery](courses/bigquery)

        **Backend Engineering**
        - Language: Python, [Go](courses/golang), Java, Node.js
        - API: REST, [gRPC](courses/grpc)
        - Database: [PostgreSQL](courses/postgres), [MongoDB](courses/mongodb)
        - Search Engine: [Elasticsearch](courses/elasticsearch)
        - Services Communication: [Apache Kafka](courses/kafka), RabbitMQ

        **Infrastructure**
        - IaaC: [Terraform](courses/terraform), Ansible
        - Container: [Docker](courses/docker), [Kubernetes](couses/kubernetes)
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
