
# Azure SQL vs Cosmos DB vs PostgreSQL

Azure provides a variety of database services for different use cases. Here's a comparison of the three main options.

---

## 1. Azure SQL Database

- PaaS SQL Server
- Built-in HA, auto-patching
- Supports T-SQL, transactions
- Ideal for: OLTP, enterprise apps, business-critical workloads

### Pricing Models

- DTU-based
- vCore-based (serverless or provisioned)

---

## 2. Azure Cosmos DB

- Globally distributed NoSQL database
- Multi-model: SQL, MongoDB, Cassandra, Gremlin, Table
- Low-latency, high-throughput
- Ideal for: IoT, telemetry, real-time analytics

### Key Features

- Multi-region replication
- SLA for latency and throughput
- Tunable consistency models

---

## 3. Azure Database for PostgreSQL

- PostgreSQL as a managed service
- Flexible Server or Single Server deployment
- Full PostgreSQL feature set with auto HA
- Ideal for: web apps, geospatial apps, open source migration

---

## 4. Comparison Summary

| Feature               | Azure SQL    | Cosmos DB   | PostgreSQL |
|-----------------------|--------------|-------------|------------|
| Model                 | Relational   | NoSQL       | Relational |
| HA Built-in           | Yes          | Yes         | Yes        |
| Scaling               | vCore/DTU    | RU/s        | vCore      |
| Global Distribution   | No           | Yes         | Limited    |
| Use Case              | OLTP, BI     | Real-time, NoSQL | OSS, LAMP stack |

---

## 5. Best Practices

- Choose based on data model: normalized → SQL, hierarchical or key-value → Cosmos
- Use Elastic Pools for multi-tenant SQL apps
- Use Private Endpoint to secure access
