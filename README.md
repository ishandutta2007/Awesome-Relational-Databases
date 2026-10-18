# Awesome-Relational-Databases

## Top Relational Databases Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on ACID Transactions, SQL Standards Compliance & Horizontal Scalability*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Relational Databases**. These tools store structured data in tables with rows and columns, enforce schema and constraints, and guarantee ACID transactions — the foundation for transactional applications, financial systems, and enterprise data stores.

**Examples** include Oracle Database, MySQL, Microsoft SQL Server, PostgreSQL, Amazon RDS, Azure SQL Database, Google Cloud SQL, CockroachDB, IBM Db2, and SingleStore (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, PostgreSQL extensions, and transparent query planning — ideal for teams prioritizing data sovereignty, avoiding Oracle licensing, and building on open standards.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Amazon RDS](https://aws.amazon.com/rds/)**  
  AWS-managed relational databases supporting **MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server**. Automated backups, Multi-AZ failover, read replicas, and Performance Insights. **Aurora** is AWS's proprietary MySQL/PostgreSQL-compatible engine with distributed storage and serverless v2 scaling.

- **[Azure SQL Database](https://azure.microsoft.com/en-us/products/azure-sql/)**  
  Microsoft's managed SQL Server engine with **DTU or vCore billing**, serverless auto-scaling, and **online vertical scaling with almost no downtime** — the best in class for resizing without interruption [citation:12]. Deep integration with Microsoft 365 and Dynamics.

- **[Google Cloud SQL](https://cloud.google.com/sql)**  
  Managed MySQL, PostgreSQL, and SQL Server on GCP. **Backup retention up to 365 days** — the longest among major cloud providers [citation:12]. Simple pricing by vCPU and memory, with committed use discounts.

- **[Google Cloud Spanner](https://cloud.google.com/spanner)**  
  **The benchmark for globally distributed, strongly consistent SQL** using TrueTime API (atomic clocks + GPS) [citation:5]. Automatic sharding across regions with no manual intervention. **Trade-offs**: proprietary SQL dialect requiring application changes, no scale-to-zero, and higher base cost [citation:6].

- **[Oracle Autonomous Database](https://www.oracle.com/)**  
  Oracle's self-driving cloud database with automated tuning, patching, and scaling. Still dominant in enterprise core banking and ERP, but **losing share as organizations migrate non-core systems to open source** [citation:7].

- **[SAP HANA](https://www.sap.com/)**  
  In-memory relational database optimized for SAP applications. Columnar storage for analytics with row-store for transactions.

- **[SingleStore](https://www.singlestore.com/)**  
  Distributed SQL database combining transactional and analytical workloads (HTAP) with MySQL wire compatibility.

## Open-Source GitHub Projects

- **[PostgreSQL](https://github.com/postgres/postgres)**  
  **The most advanced open-source relational database** — PostgreSQL License (permissive). **Only major database showing sustained growth in 2026** — DB-Engines trend +45.56 points year-over-year, closing to within 6 points of SQL Server [citation:13]. **Full SQL standard compliance** with window functions, CTEs, and materialized views. **Native JSONB** for semi-structured data. **Extension ecosystem**: PostGIS for geospatial, **pgvector for AI vector search**, TimescaleDB for time-series. **PostgreSQL 18** added async I/O (io_uring) delivering up to **3x speedup on I/O-heavy workloads** [citation:2]. **MVCC never blocks readers** — benchmarked at **2,886 OLTP TPS vs MySQL 8.4's 436 TPS** [citation:20]. **Best for new projects** unless you have a specific reason otherwise [citation:1].

- **[MySQL](https://github.com/mysql/mysql-server)**  
  **The world's most popular open-source database** — GPL-2.0 licensed. **The default for Web applications** (WordPress, Drupal, most PHP stacks) with the largest ecosystem of tutorials and hosting options [citation:20]. **Trade-offs**: **Oracle's commercialization strategy is straining community trust** — commercial license price increases and feature gating have driven users to MariaDB and Percona [citation:7]. **MySQL 8.4 benchmarked at 436 OLTP TPS** — 6.6x slower than PostgreSQL under concurrent workloads [citation:20]. **Still viable for read-heavy web apps** where its simplicity and ubiquity matter more than raw OLTP throughput.

- **[MariaDB](https://github.com/MariaDB/server)**  
  **The community-driven MySQL fork** — GPL-2.0 licensed. **Drop-in replacement for most MySQL applications** with zero code changes [citation:2]. **Faster than MySQL on pure reads and inserts** — benchmarked at **6,949 read TPS and 8,093 insert TPS**, outperforming both MySQL and PostgreSQL on single-operation workloads [citation:20]. **Galera Cluster provides true multi-master synchronous replication** — MySQL only offers single-primary topology [citation:2]. **MariaDB 11.8** added built-in vector search [citation:2]. **Trade-offs**: diverging from MySQL on newer features; no native logical replication [citation:20]. **Best for teams wanting MySQL compatibility with better performance and community governance**.

- **[CockroachDB](https://github.com/cockroachdb/cockroach)**  
  **The open-source Spanner-inspired distributed SQL database** — BSL/CCL licensed. **Serializable isolation, horizontal scaling, automated failover and repair** [citation:5]. **PostgreSQL wire compatibility** for most syntax. **The choice for teams wanting geo-distributed SQL without cloud vendor lock-in** [citation:5]. **Trade-offs**: BSL license is not OSI-approved; operational complexity higher than single-node PostgreSQL.

- **[TiDB](https://github.com/pingcap/tidb)**  
  **PingCAP's HTAP distributed SQL database** — Apache 2.0 licensed. **MySQL compatible** with **TiFlash columnar engine** for real-time analytics without ETL [citation:16]. **The migration path from MySQL is well-documented**: compatibility assessment, schema validation, application testing, then cutover with seconds of downtime [citation:16]. **Best for SaaS platforms needing horizontal scale and real-time operational analytics in one system** [citation:16].

- **[YugabyteDB](https://github.com/yugabyte/yugabyte-db)**  
  **Distributed SQL with PostgreSQL (YSQL) and Redis (YEDIS) compatibility** — Apache 2.0 licensed [citation:4]. **Raft consensus for strong consistency** with separated query and storage layers [citation:5]. **Best for PostgreSQL-oriented teams needing geo-distributed SQL** with multi-cloud deployment [citation:16].

- **[SQLite](https://github.com/sqlite/sqlite)**  
  **The most deployed database in the world** — public domain. **Embedded, zero-configuration, serverless** — the database engine inside phones, browsers, and embedded systems. **Best for local storage, prototyping, and read-heavy embedded workloads**.

- **[DuckDB](https://github.com/duckdb/duckdb)**  
  **The analytical SQL database that runs in-process** — MIT licensed [citation:3]. **PostgreSQL-inspired SQL** with **direct read/write of CSV, JSON, Parquet, and Iceberg** [citation:3]. **Not a transactional replacement** — designed for OLAP and data wrangling. **Best for analytics on local files** and embedded analytical workloads.

### Additional Strong Open-Source Options

- **Percona Server for MySQL** — Enhanced MySQL fork with better performance and diagnostics. **The conservative choice for MySQL compatibility** — "求稳选 Percona" (choose Percona for stability) [citation:2].
- **Percona Server for PostgreSQL** — Enhanced PostgreSQL distribution with enterprise tooling.
- **Vitess** — MySQL sharding middleware powering YouTube. Apache 2.0 licensed [citation:4].
- **Citus** — PostgreSQL extension for distributed multi-tenant SaaS. AGPL licensed [citation:17].
- **TimescaleDB** — PostgreSQL extension for time-series data.
- **PostGIS** — PostgreSQL extension for geospatial data.
- **pgvector** — PostgreSQL extension for vector similarity search, critical for AI applications [citation:13].

**Frameworks for building custom systems**: Combine **PostgreSQL** for general-purpose transactional work with the strongest ecosystem and sustained momentum, **MariaDB** or **Percona Server** for MySQL compatibility with better performance, **CockroachDB** or **TiDB** for distributed SQL when single-node write throughput becomes the ceiling, **SQLite** for embedded and local storage, and **DuckDB** for analytical workloads on files — to build a relational data layer tailored to your consistency requirements, scale targets, and licensing constraints.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Relational databases differ significantly in licensing, performance profile, and operational complexity. **PostgreSQL is the only major database growing in 2026** — closing to within 6 points of SQL Server on DB-Engines [citation:13]. **MySQL 8.4 underperforms significantly on OLTP** — 436 TPS vs PostgreSQL's 2,886 and MariaDB's 2,758 [citation:20]. **Oracle's licensing costs and commercialization strategy** drive ongoing migration to open source [citation:7]. **CockroachDB's BSL license is not OSI-approved** — evaluate against your compliance requirements. **Spanner's SQL dialect is not fully compatible** with MySQL, PostgreSQL, or T-SQL — migration requires application changes [citation:6]. **Benchmarks are workload-dependent** — validate against your specific query patterns and concurrency profile.
- Self-hosted open-source solutions require proper backup strategies, connection pooling, and monitoring. PostgreSQL's `VACUUM` overhead grows with long-running transactions; MySQL's InnoDB row-locking creates contention under high concurrency [citation:20].

---

**Made for database administrators, backend engineers, and architects building transactional data systems.**
Let's make relational databases more open, performant, and operationally transparent.
