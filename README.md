# qadmindemo

QuickAdmin.Net demo app image.

## Quick Start
```bash
docker run -it -p 18088:5000 ghcr.io/munanwang/qadmindemo
```

## Environment Variables

`QADMIN_DB_TYPE`  

Database type: `Sqlite`/`SqlServer`/`Oracle`/`PostgreSQL`/`MySql`/`Firebird`/`Dameng`/`KingbaseES`, etc.

`QADMIN_DB_CONNSTRING`  

Database connection string.  

`QADMIN_MONITOR_SQL_COMMAND`  

Enables monitoring of executed SQL commands.  
When set to `yes`, the system will print each executed SQL command to the console.

​**Important note:​**​  
Both `QADMIN_DB_TYPE` and `QADMIN_DB_CONNSTRING` must be provided together if you want to use an external database. If neither is provided, the system will use the built-in Sqlite database.

## Examples

- Use with PostgreSQL
```bash
docker run -it -p 18088:5000 \
  -e QADMIN_DB_TYPE=PostgreSQL \
  -e QADMIN_DB_CONNSTRING="Host=host.docker.internal;Port=5432;Username=qadmin;Password=123456;Database=qadmindemo" \
  ghcr.io/munanwang/qadmindemo
```

- Enable SQL Monitoring:  
```bash
docker run -it -p 18088:5000 \
  -e QADMIN_MONITOR_SQL_COMMAND=yes \
  ghcr.io/munanwang/qadmindemo
```

