---
title: 2. PostgreSQL for Developers
summary: PostgreSQL for Developer
type: docs

sections:
  - block: collection
    id: postgres
    content:
      title: Courses
      filters:
        folders:
          - postgres 
    design:
      view: article-grid
---

aas
- Advanced SQL Techniques: Complex queries, window functions, CTEs, and aggregate functions.
- Data Modeling for Applications: Tips for modeling data that scales and suits application logic.
- JSON and JSONB: Working with semi-structured data, best practices, and performance tips.
- Handling Schema Changes: Strategies for schema migrations, zero-downtime migrations, and versioning.
- Database Testing: Techniques for unit and integration testing for PostgreSQL queries.
- ORMs and PostgreSQL: Overview of common ORMs (like SQLAlchemy, Django ORM, etc.), how they work, and when to avoid or leverage them.
- Error Handling: Handling database errors and managing exceptions in application code.
- Working with Triggers and Functions: How triggers and functions can enhance application logic directly in the database.
- Using Extensions: Useful extensions for developers (e.g., PostGIS for GIS, pg_trgm for text search, and UUIDs).
- Ways to export data out of PostgreSQL: 
  - Native: `pg_dump`, `COPY` or `psq \copy`