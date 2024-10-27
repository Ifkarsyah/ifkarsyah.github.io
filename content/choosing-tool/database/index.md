---
title: "Database Comparison: PostgreSQL vs. MySQL"
---

TLDR: use PostgreSQL unless you have no choice because you work in company that use MySQL

https://www.reddit.com/r/node/comments/rv6u8u/why_do_you_choose_mysql_over_postgres/
https://www.reddit.com/r/PostgreSQL/comments/tldork/in_what_circumstances_is_mysql_better_than/
https://www.reddit.com/r/PostgreSQL/comments/xblooo/convince_me_to_choose_postgresql_over_mysql/
https://www.reddit.com/r/golang/comments/16hn0u3/mysql_or_postgres/
https://www.bytebase.com/blog/postgres-vs-mysql/
https://www.integrate.io/blog/postgresql-vs-mysql-which-one-is-better-for-your-use-case/
https://www.datacamp.com/blog/postgresql-vs-mysql


## Popularity
Why? Better community supports
### Google Trends

### Big Company Adoption

### Distribution of Commit
MySQL is so Oracle, kind of the same with Delta Lake by Databricks.
https://www.datacamp.com/blog/postgresql-vs-mysql

## Compatibility

Why? You don't need to rewrite SQL you have in OLTP and OLAP.

### PostgreSQL-compatible Database
RisingWave, CitusDB, CockroachDB
https://github.com/ApsaraDB/PolarDB-for-PostgreSQL
https://www.yugabyte.com/postgresql/compare-postgresql-compatibility/
https://risingwave.com/blog/top-5-postgresql-compatible-database/

### MySQL-compatible Database
StarRocks


## Benchmarking
sysbench
HammerDB