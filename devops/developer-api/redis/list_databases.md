List Databases
cURL
Copy
Ask AI
```
curl --request GET \
  --url https://api.upstash.com/v2/redis/databases \
  --header 'Authorization: Basic <encoded-value>'
```

200
Copy
Ask AI
```
[
  {
    "database_id": "96ad0856-03b1-4ee7-9666-e81abd0349e1",
    "database_name": "MyRedis",
    "region": "global",
    "port": 6379,
    "creation_time": 1752649602,
    "state": "active",
    "endpoint": "beloved-stallion-58500",
    "tls": true,
    "db_max_clients": 10000,
    "db_max_request_size": 10485760,
    "db_disk_threshold": 107374182400,
    "db_max_entry_size": 104857600,
    "db_memory_threshold": 3221225472,
    "db_max_commands_per_second": 10000,
    "db_request_limit": 8024278031528737000,
    "type": "paid",
    "budget": 360,
    "primary_region": "us-east-1",
    "primary_members": [
      "us-east-1"
    ],
    "all_members": [
      "us-east-1"
    ],
    "eviction": false,
    "auto_upgrade": false,
    "consistent": false,
    "modifying_state": "",
    "db_resource_size": "L",
    "db_type": "pebble",
    "db_conn_idle_timeout": 21600000000000,
    "db_lua_timeout": 250000000,
    "db_lua_credits_per_min": 10000000000,
    "db_store_max_idle": 900000000000,
    "db_max_loads_per_sec": 1000000,
    "db_acl_enabled": "false",
    "db_acl_default_user_status": "true",
    "db_eviction": false,
    "last_plan_upgrade_time": 0,
    "replicas": 5,
    "customer_id": "example@upstash.com",
    "daily_backup_enabled": false,
    "read_regions": [
      "us-east-2"
    ],
    "securityAddons": {
      "ipWhitelisting": false,
      "vpcPeering": false,
      "privateLink": false,
      "tlsMutualAuth": false,
      "encryptionAtRest": false
    },
    "prometheus_enabled": "false",
    "prod_pack_enabled": false
  }
]
```

GET
/
redis
/
databases
Try it
List Databases
cURL
Copy
Ask AI
```
curl --request GET \
  --url https://api.upstash.com/v2/redis/databases \
  --header 'Authorization: Basic <encoded-value>'
```

200
Copy
Ask AI
```
[
  {
    "database_id": "96ad0856-03b1-4ee7-9666-e81abd0349e1",
    "database_name": "MyRedis",
    "region": "global",
    "port": 6379,
    "creation_time": 1752649602,
    "state": "active",
    "endpoint": "beloved-stallion-58500",
    "tls": true,
    "db_max_clients": 10000,
    "db_max_request_size": 10485760,
    "db_disk_threshold": 107374182400,
    "db_max_entry_size": 104857600,
    "db_memory_threshold": 3221225472,
    "db_max_commands_per_second": 10000,
    "db_request_limit": 8024278031528737000,
    "type": "paid",
    "budget": 360,
    "primary_region": "us-east-1",
    "primary_members": [
      "us-east-1"
    ],
    "all_members": [
      "us-east-1"
    ],
    "eviction": false,
    "auto_upgrade": false,
    "consistent": false,
    "modifying_state": "",
    "db_resource_size": "L",
    "db_type": "pebble",
    "db_conn_idle_timeout": 21600000000000,
    "db_lua_timeout": 250000000,
    "db_lua_credits_per_min": 10000000000,
    "db_store_max_idle": 900000000000,
    "db_max_loads_per_sec": 1000000,
    "db_acl_enabled": "false",
    "db_acl_default_user_status": "true",
    "db_eviction": false,
    "last_plan_upgrade_time": 0,
    "replicas": 5,
    "customer_id": "example@upstash.com",
    "daily_backup_enabled": false,
    "read_regions": [
      "us-east-2"
    ],
    "securityAddons": {
      "ipWhitelisting": false,
      "vpcPeering": false,
      "privateLink": false,
      "tlsMutualAuth": false,
      "encryptionAtRest": false
    },
    "prometheus_enabled": "false",
    "prod_pack_enabled": false
  }
]
```

#### Authorizations
​
Authorization
string
header
required
Basic authentication header of the form `Basic <encoded-value>`, where `<encoded-value>` is the base64-encoded string `username:password`.
#### Response
200 - application/json
OK
The response is of type `object[]`.
Was this page helpful?
YesNo
Suggest editsRaise issue
HTTP Status CodesGet Database
Assistant
Responses are generated using AI and may contain mistakes.
