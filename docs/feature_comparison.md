# Percona Server for MySQL feature comparison

*Percona Server for MySQL* is a free, fully compatible, enhanced, and open source drop-in replacement for any MySQL database. It provides superior performance, scalability, and instrumentation.

*Percona Server for MySQL* is trusted by thousands of enterprises to provide better performance and concurrency for their most demanding workloads. It delivers higher value to MySQL server users with optimized performance, greater performance scalability and availability, enhanced backups, and increased visibility.

We provide these benefits by significantly enhancing *Percona Server for MySQL* as
compared to the standard *MySQL* database server:

| Features                          | Percona Server for MySQL 8.0.13 | MySQL 8.0.13 |
|-----------------------------------|---------------------------------|--------------|
| Open source                       | Yes                             | Yes          |
| ACID Compliance                   | Yes                             | Yes          |
| Multi-Version Concurrency Control | Yes                             | Yes          |
| Row-Level Locking                 | Yes                             | Yes          |
| Automatic Crash Recovery          | Yes                             | Yes          |
| Table Partitioning                | Yes                             | Yes          |
| Views                             | Yes                             | Yes          |
| Subqueries                        | Yes                             | Yes          |
| Triggers                          | Yes                             | Yes          |
| Stored Procedures                 | Yes                             | Yes          |
| Foreign Keys                      | Yes                             | Yes          |
| Window Functions                  | Yes                             | Yes          |
| Common Table Expressions          | Yes                             | Yes          |
| Geospatial Features (GIS, SPRS)   | Yes                             | Yes          |
| GTID Replication                  | Yes                             | Yes          |
| Group Replication                 | Yes                             | Yes          |
| MyRocks Storage Engine            | Yes                             | No           |
| TokuDB Storage Engine             | Yes                             | No           |

## Improvements for developers

| Feature                              | Percona Server for MySQL 8.0.13 | MySQL 8.0.13 |
|--------------------------------------|---------------------------------|--------------|
| NoSQL Socket-Level Interface         | Yes                             | Yes          |
| X API Support                        | Yes                             | Yes          |
| JSON Functions                       | Yes                             | Yes          |
| InnoDB Full-Text Search Improvements | Yes                             | No           |
| Extra Hash/Digest Functions          | Yes                             | No           |

## Extra diagnostic features

| Feature                                | Percona Server for MySQL 8.0.13 | MySQL 8.0.13 |
|----------------------------------------|---------------------------------|--------------|
| INFORMATION_SCHEMA Tables              | 95                              | 65           |
| Global Performance and Status Counters | 853                             | 434          |
| Optimizer Histograms                   | Yes                             | Yes          |
| Per-Table Performance Counters         | Yes                             | No           |
| Per-Index Performance Counters         | Yes                             | No           |
| Per-User Performance Counters          | Yes                             | No           |
| Per-Client Performance Counters        | Yes                             | No           |
| Per-Thread Performance Counters        | Yes                             | No           |
| Enhanced SHOW ENGINE INNODB STATUS     | Yes                             | No           |
| Temporary tables Information           | Yes                             | No           |
| Extended Slow Query Logging            | Yes                             | No           |
| User Statistics                        | Yes                             | No           |

## Performance & scalability enhancements

| Feature                                          | Percona Server for MySQL 8.0.13 | MySQL 8.0.13 |
|--------------------------------------------------|---------------------------------|--------------|
| InnoDB Resource Groups                           | Yes                             | Yes          |
| Configurable Page Sizes                          | Yes                             | Yes          |
| Contention-Aware Transaction Scheduling          | Yes                             | Yes          |
| Improved Scalability by Splitting Mutexes        | Yes                             | Yes          |
| Improved MEMORY Storage Engine                   | Yes                             | No           |
| Improved Flushing                                | Yes                             | No           |
| Parallel Doublewrite Buffer                      | Yes                             | No           |
| Configurable Fast Index Creation                 | Yes                             | No           |
| Per-Column Compression for VARCHAR/BLOB and JSON | Yes                             | No           |
| Compressed Columns with Dictionaries             | Yes                             | No           |

## Security features

| Feature                      | Percona Server for MySQL 8.0.13 | MySQL 8.0.13    |
|------------------------------|---------------------------------|-----------------|
| SQL Roles                    | Yes                             | Yes             |
| SHA-2 Based Password Hashing | Yes                             | Yes             |
| Password Rotation Policy     | Yes                             | Yes             |
| PAM Authentication           | Yes                             | Enterprise Only |
| Audit Logging Plugin         | Yes                             | Enterprise Only |

## Encryption features

| Feature                                                           | Percona Server for MySQL 8.0.13 | MySQL 8.0.13 |
|-------------------------------------------------------------------|---------------------------------|--------------|
| Storing Keyring in a File                                         | Yes                             | Yes          |
| Storing Keyring in Hashicorp Vault                                | Yes                             | No           |
| Encrypt InnoDB Data                                               | Yes                             | Yes          |
| Encrypt InnoDB Logs                                               | Yes                             | Yes          |
| Encrypt Built-in InnoDB Tablespaces (General, System, Undo, Temp) | Yes                             | No           |
| Encrypt Binary Logs                                               | Yes                             | No           |
| Encrypt Temporary Files                                           | Yes                             | No           |
| Key Rotation with Scrubbing                                       | Yes                             | No           |
| Enforce Encryption                                                | Yes                             | No           |

## Operational improvements

| Feature                                                    | Percona Server for MySQL 8.0.13 | MySQL 8.0.13    |
|------------------------------------------------------------|---------------------------------|-----------------|
| Atomic DDL                                                 | Yes                             | Yes             |
| Transactional Data Dictionary                              | Yes                             | Yes             |
| Instant DDL                                                | Yes                             | Yes             |
| SET PERSIST                                                | Yes                             | Yes             |
| Invisible Indexes                                          | Yes                             | Yes             |
| Changed Page Tracking                                      | Yes                             | No              |
| Threadpool                                                 | Yes                             | Enterprise Only |
| Backup Locks                                               | Yes                             | Yes             |
| Extended SHOW GRANTS                                       | Yes                             | No              |
| Improved Handling of Corrupted Tables                      | Yes                             | No              |
| Ability to Kill Idle Transactions                          | Yes                             | No              |
| Improvements to START TRANSACTION WITH CONSISTENT SNAPSHOT | Yes                             | No              |

