---
# Display name
title: Ferdian Ifkarsyah

# Name pronunciation (optional)
name_pronunciation: ''

# Full name (for SEO)
first_name: Ferdian
last_name: Ifkarsyah

# Status emoji
status:
  icon: ☕️

# Is this the primary user of the site?
superuser: true

# Highlight the author in author lists? (true/false)
highlight_name: true

# Role/position/tagline
role: Data Infrastructure Engineer

# Organizations/Affiliations to display in Biography blox
# organizations:
#   - name: Ifkarsyah
#     url: https://ifkarsyah.github.io

# Social network links
# Need to use another icon? Simply download the SVG icon to your `assets/media/icons/` folder.
profiles:
  # - icon: at-symbol
  #   url: 'mailto:your-email@example.com'
  #   label: E-mail Me
  - icon: brands/github
    url: https://github.com/ifkarsyah
  - icon: brands/linkedin
    url: https://www.linkedin.com/in/ifkarsyah/
  - icon: brands/x
    url: https://twitter.com/ifkarsyah
  - icon: brands/instagram
    url: https://www.instagram.com/ifkarsyah

interests:
  - System Design
  - Data Infrastructure
  - Database Engineering

education:
  - area: BSc Computer Science
    institution: Bandung Institute of Technology
    date_start: 2017-08-01
    date_end: 2021-10-01
    summary: |
      Thesis on _Optimized why to learn Japanese Kanji using Knowledge Graph_. Supervised by [Prof Joe Smith](https://example.com). 

      Courses included:
      - Operating System
      - Parallel and Distributed System
      - Database System
      - Big Data
    button:
      text: 'Read Final Thesis'
      url: 'https://example.com'
work:
  - position: Fazz
    company_name: Senior Data Engineer
    company_url: 'https://fazz.com/'
    company_logo: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTckxZrcZeAqB1rHHE60WdukB5KAg0q_1hk0w&s'
    date_start: 2024-05-01
    date_end: ''
    summary: |2-
      Responsibilities include:
      - Reduced RDS pipeline steps from 5 to 3 by eliminating redundant copy steps and developed a Terraform module for automating GCP Storage Transfer creation.
      - Minimized load on the production database by migrating recurring ad-hoc analytics queries to BigQuery
  - position: L4 Data Infrastructure Engineer
    company_name: Xendit
    company_url: 'https://www.xendit.co/en/'
    company_logo: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTp1PjQagXJnoUqy0ZdzThs5XETP_ncL918pQ&s'
    date_start: 2022-10-01
    date_end: 2024-03-31
    summary: |
      Responsibilities include:
      - Setup data infrastructure
      - Cost optimization
      - Knowledge sharing

      Accomplishments: 
      - Achieved $7,400 monthly cost reduction by transitioning Trino from multizone to active-standby architecture.
      - Provisioned Kubernetes cluster from scratch, and migrated Trino from EMR, resulting in 80% cost reduction
      - Developed a Web UI to team’s data platform using Flask API and Retool, reducing manual ticket by 90%.
      - Implemented instance right-sizing strategies and reserved instances, resulting in a $2,300 monthly cost reduction
  - position: L3 Data Engineer
    company_name: Xendit
    company_url: 'https://www.xendit.co/en/'
    company_logo: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTp1PjQagXJnoUqy0ZdzThs5XETP_ncL918pQ&s'
    date_start: 2021-10-01
    date_end: 2022-10-01
    summary: |
      Accomplishments: 
      - Accelerated user journey analysis by 10x by shifting from batch event tracking to real-time using Kafka.
      - Optimized pipeline queue time by 60% using Airflow TaskGroup to group and manage heavy workload tasks.
      - Automated Spark clusters provisioning using Terraform reduced processing time from 2 days to 10 minutes.
      - Developed a system to ensure heavy dbt pipelines includes partitioning key, minimizing full table scans by 20%
  - position: L2 Junior Data Engineer
    company_name: Xendit
    company_url: 'https://www.xendit.co/en/'
    company_logo: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTp1PjQagXJnoUqy0ZdzThs5XETP_ncL918pQ&s'
    date_start: 2021-03-01
    date_end: 2021-10-01
    summary: |
      Accomplishments: 
      - Introduced Presto long query alerting system that reduced p99 query time from 2 minutes to 30 seconds.
      - Integrated 2000+ lines of custom Python ETL code contributed by multiple users into a centralized library.
      - Developed a Web UI to team’s data platform using Flask API and Retool, reducing manual ticket by 90%.
      - Ingested 100+ tables from PostgreSQL and MongoDB across the companies into data lakehouse.

# Skills
# Add your own SVG icons to `assets/media/icons/`
skills:
  - name: Technical Skills
    items:
      - name: Data Engineering
        description: ''
        percent: 100
        icon: devicon/apachespark
      - name: Backend Development
        description: ''
        percent: 80
        icon: devicon/postman
      - name: Database
        description: ''
        percent: 40
        icon: devicon/postgresql
      - name: Infrastructure
        description: ''
        percent: 40
        icon: devicon/kubernetes
  - name: Hobbies
    color: '#eeac02'
    color_border: '#f0bf23'
    items:
      - name: Hiking
        description: ''
        percent: 60
        icon: person-simple-walk
      - name: Chess
        description: ''
        percent: 100
        icon: academicons/springer
      - name: Photography
        description: ''
        percent: 80
        icon: camera

languages:
  - name: English
    percent: 100
  - name: Indonesia
    percent: 100
  - name: Malay
    percent: 80

# Awards.
#   Add/remove as many awards below as you like.
#   Only `title`, `awarder`, and `date` are required.
#   Begin multi-line `summary` with YAML's `|` or `|2-` multi-line prefix and indent 2 spaces below.
awards:
  - title: '[National] First Place, Tokopedia DevCamp 2021'
    url: https://academy.tokopedia.com/events/dev-camp/
    date: '2021-09-01'
    awarder: Tokopedia
    icon: tokopedia
    summary: |
      Won the hackathon competition out of 4000 contestants by creating \href{https://github.com/ifkarsyah/pasin}{Pasin}, a web service to recommend the best clothing sizes for marketplace customers.
  - title: '[National] Finalist, SEA Compfest 2020'
    url: https://compfest.id/
    date: '2020-08-01'
    awarder: edX
    icon: edx
    summary: |
      Selected as one of 20 participants from more than 600 applicants to study agile software engineering, docker, microservices, docker, and DevOps. 
  - title: '[Regional] Finalist, ACM-ICPC Asia Jakarta 2019'
    url: https://competition.binus.ac.id/icpc2019/
    certificate_url: https://competition.binus.ac.id/icpc2019/
    date: '2019-08-01'
    awarder: datacamp
    icon: datacamp
    summary: |
      Advanced to finals through competition between more than 500 teams. Codes with C++ for competitive programming.
---

## About Me

Hi, I'm a Software Engineer focused on data infrastructure. I develop and deploy big data software on Kubernetes clusters using tools like Apache Trino, Helm, ArgoCD, and Terraform. My job involves improving query performance and scalability for data analytics platforms while ensuring proper data access and security for each product team. With three years of experience in data engineering, I've work with languages like Python, Java, Go, and Scala. I also love sharing what I know on my blog, where I write about data engineering, big data, and related topics. I'm really passionate about optimizing data infrastructure and tackling complex data problems.
