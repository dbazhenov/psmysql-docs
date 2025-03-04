# MyRocks column families

*MyRocks* stores all data in a single server instance as a collection of
key-value pairs within the log structured merge tree data structure. This is a
flat data structure that requires that keys be unique throughout the whole data
structure. *MyRocks* incorporates table IDs and index IDs into the keys.

Each key-value pair belongs to a column family. It is a data structure similar
in concept to tablespaces. Each column family has distinct attributes, such as
block size, compression, sort order, and MemTable. Utilizing these attributes,
*MyRocks* effectively uses column families to store indexes.

On system initialization, *MyRocks* creates two column families.  The
`__system__` column family is reserved by *MyRocks*; no user created tables or
indexes belong to this column family.  The `default` column family is the
location for the indexes created by the user when you a column family is not
explicitly specified.

To be able to apply a custom block size, compression, or sort order you need to
create an index in its own column family using the `COMMENT` clause.

The following example demonstrates how to place the `PRIMARY KEY` into the
cf1 column family and the index `kb` — into the cf2 column family.

```sql
CREATE TABLE t1 (a INT, b INT,
PRIMARY KEY(a) COMMENT 'cfname=cf1',
KEY kb(b) COMMENT 'cf_name=cf2')
ENGINE=ROCKSDB;
```

The column family name is specified as the value of the cf_name attribute at
the beginning of the `COMMENT` clause. The name is case sensitive and may not
contain leading or trailing whitespace characters.

The `COMMENT` clause may contain other information following the semicolon
character (;) after the column family name: ‘cfname=foo; special column
family’. If the column family cannot be created, *MyRocks* uses the default
column family.

!!! warning

    The `cf_name` attribute must be all lowercase. Place the equals sign (=) in front of the column family name without any whitespace on both sides of it.
    
    ```text
    COMMENT 'cfname=Foo; Creating the Foo family name'
    ```

!!! admonition "See also"

    Using `COMMENT` to Specify Column Family Names with Multiple Table Partitions
    https://github.com/facebook/mysql-5.6/wiki/Column-Families-on-Partitioned-Tables.

### Controlling the number of column families to reduce memory consumption

Each column family has its own MemTable. It is an in-memory data structure where
data are written to before they are flushed to SST files. The queries also use
MemTables first. To reduce the overall memory consumption, the number of active
column families should stay low.

<!-- Application: PS-8.0 not PS-5.7 -->
With the option `|opt.no-create-column-family|` set to true, the `COMMENT`
clause will not treat cf_name as a special token; it will not be possible to
create column families using the `COMMENT` clause.

## Column family options

On startup, the server applies the `|opt.default-cf-options|` option to all
existing column families. You may use the `|opt.override-cf-options|` option to
override the value of any attribute of a chosen column family.

Note that the options `|opt.dcfo|` and `|opt.ocfo|` are read-only at runtime.

At runtime, use the the `|opt.update-cf-options|` option to update some column
family attributes.

<!-- RocksDB options: Each is defined with and without the rocksdb
prefix. Some have the abbreviated syntax -->
