- you can this hack:

```
// In classes/database/Connection.php (your actual file path may vary)
switch (substr($version,0,3)) {
    case '15.': return 'Postgres'; break;
    case '16.': return 'Postgres'; break;
    // ... other cases
    default: return 'Postgres'; break; // Add this line!
}
```

- make the Postgres Replicated user `admin` and provide these Powers:

```
ALTER USER admin WITH SUPERUSER CREATEDB CREATEROLE REPLICATION BYPASSRLS;
```
