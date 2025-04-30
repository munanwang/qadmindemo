# qadmindemo

[QuickAdmin.Net](https://quickadmin.net) demo app image.

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
When set to `yes`, each executed SQL command will be printed to the console during the running of the application.

​**Important note:​**​  
Both `QADMIN_DB_TYPE` and `QADMIN_DB_CONNSTRING` must be provided together if you want to use an external database. If neither is provided, the application will use the built-in Sqlite database.

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

