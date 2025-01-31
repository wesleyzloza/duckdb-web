---
layout: docu
title: inet Extension
---

The `inet` extension defines the `INET` data type for storing [IPv4 network addresses](https://en.wikipedia.org/wiki/Internet_Protocol_version_4).
It supports the [CIDR notation](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing#CIDR_notation) for subnet masks (e.g., `198.51.100.0/22`).

## Installing and Loading

To install and load the `inet` extension, run:

```sql
INSTALL inet;
LOAD inet;
```

## Examples

```sql
SELECT '127.0.0.1'::INET AS addr;
```

|   addr    |
|-----------|
| 127.0.0.1 |

```sql
CREATE TABLE tbl (id INTEGER, ip INET);
INSERT INTO tbl VALUES (1, '192.168.0.0/16'), (2, '127.0.0.1'), (2, '8.8.8.8');
SELECT * FROM tbl;
```

| id |       ip       |
|---:|----------------|
| 1  | 192.168.0.0/16 |
| 2  | 127.0.0.1      |
| 2  | 8.8.8.8        |

## GitHub

The `inet` extension is part of the [main DuckDB repository](https://github.com/duckdb/duckdb/tree/main/extension/inet).
