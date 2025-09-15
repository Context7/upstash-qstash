Rename Database
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/rename/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "name": "<string>"
}'
```

200
Copy
Ask AI
```
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
```

POST
/
redis
/
rename
/
{id}
Try it
Rename Database
cURL
Copy
Ask AI
```
curl --request POST \
  --url https://api.upstash.com/v2/redis/rename/{id} \
  --header 'Authorization: Basic <encoded-value>' \
  --header 'Content-Type: application/json' \
  --data '{
  "name": "<string>"
}'
```

200
Copy
Ask AI
```
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
```

#### Authorizations
​
Authorization
string
header
required
Basic authentication header of the form `Basic <encoded-value>`, where `<encoded-value>` is the base64-encoded string `username:password`.
#### Path Parameters
​
id
string
required
The ID of the database to be renamed
#### Body
application/json
​
name
string
required
The new name of the database
#### Response
200 - application/json
Database renamed successfully
​
database_id
string
ID of the database
Example:
`"96ad0856-03b1-4ee7-9666-e81abd0349e1"`
​
database_name
string
Name of the database
Example:
`"MyRedis"`
​
region
enum<string>
The region where database is hosted
Available options: 
`global`
Example:
`"global"`
​
port
integer
Database port for clients to connect
Example:
`6379`
​
creation_time
integer
Creation time of the database as Unix time
Example:
`1752649602`
​
state
enum<string>
State of database
Available options: 
`active`, 
`suspended`, 
`passive`
Example:
`"active"`
​
endpoint
string
Endpoint identifier or hostname of the database (may be a slug like "beloved-stallion-58500" or a full host)
Example:
`"beloved-stallion-58500"`
​
tls
boolean
TLS/SSL is enabled or not
Example:
`true`
​
db_max_clients
integer
Max number of concurrent clients can be opened on this database currently
Example:
`10000`
​
db_max_request_size
integer
Max size of a request that will be accepted by the database currently(in bytes)
Example:
`10485760`
​
db_disk_threshold
integer
Total disk size limit that can be used for the database currently(in bytes)
Example:
`107374182400`
​
db_max_entry_size
integer
Max size of an entry that will be accepted by the database currently(in bytes)
Example:
`104857600`
​
db_memory_threshold
integer
Max size of a memory the database can use(in bytes)
Example:
`3221225472`
​
db_max_commands_per_second
integer
Max number of commands can be sent to the database per second
Example:
`10000`
​
db_request_limit
integer
Total number of commands can be sent to the database
Example:
`8024278031528737000`
​
type
enum<string>
Payment plan of the database
Available options: 
`free`, 
`payg`, 
`pro`, 
`paid`
Example:
`"paid"`
​
budget
integer
Allocated monthly budget for the database
Example:
`360`
​
primary_region
enum<string>
Primary region of the database cluster
Available options: 
`ap-south-1`, 
`ap-southeast-1`, 
`ap-southeast-2`, 
`ap-northeast-1`, 
`eu-west-1`, 
`eu-west-2`, 
`eu-central-1`, 
`us-east-1`, 
`us-west-1`, 
`us-west-2`, 
`us-east-2`, 
`sa-east-1`, 
`ca-central-1`
Example:
`"us-east-1"`
​
primary_members
string[]
List of primary regions in the database cluster
Example:
```
["us-east-1"]
```

​
all_members
string[]
List of all regions in the database cluster
Example:
```
["us-east-1"]
```

​
eviction
boolean
Entry eviction is enabled
Example:
`false`
​
auto_upgrade
boolean
Automatic upgrade capability is enabled
Example:
`false`
​
consistent
boolean
Strong consistency mode is enabled
Example:
`false`
​
modifying_state
string
Current modifying state of the database
Example:
`""`
​
db_resource_size
enum<string>
Resource allocation tier
Available options: 
`S`, 
`M`, 
`L`, 
`XL`, 
`XXL`, 
`3XL`
Example:
`"L"`
​
db_type
enum<string>
Database storage engine type
Available options: 
`bolt`, 
`badger`, 
`pebble`
Example:
`"pebble"`
​
db_conn_idle_timeout
integer
Connection idle timeout in nanoseconds
Example:
`21600000000000`
​
db_lua_timeout
integer
Lua script execution timeout in nanoseconds
Example:
`250000000`
​
db_lua_credits_per_min
integer
Lua script execution credits per minute
Example:
`10000000000`
​
db_store_max_idle
integer
Store connection idle timeout in nanoseconds
Example:
`900000000000`
​
db_max_loads_per_sec
integer
Maximum load operations per second
Example:
`1000000`
​
db_acl_enabled
enum<string>
Access Control List enabled status
Available options: 
`true`, 
`false`
Example:
`"false"`
​
db_acl_default_user_status
enum<string>
Default user access status in ACL
Available options: 
`true`, 
`false`
Example:
`"true"`
​
db_eviction
boolean
Database-level eviction policy status
Example:
`false`
​
last_plan_upgrade_time
integer
Unix timestamp of the last plan upgrade
Example:
`0`
​
replicas
integer
Replica factor of the database
Example:
`5`
​
customer_id
string
Owner identifier of the database (may be email or marketplace-scoped email)
Example:
`"example@upstash.com"`
​
daily_backup_enabled
boolean
Whether daily backup is enabled
Example:
`false`
​
read_regions
string[]
Array of read regions of the database
Example:
```
["us-east-2"]
```

​
securityAddons
object
Security add-ons and their enablement status
Show child attributes
Example:
```
{  
  "ipWhitelisting": false,  
  "vpcPeering": false,  
  "privateLink": false,  
  "tlsMutualAuth": false,  
  "encryptionAtRest": false  
}
```

​
prometheus_enabled
enum<string>
Prometheus integration enabled status
Available options: 
`true`, 
`false`
Example:
`"false"`
​
prod_pack_enabled
boolean
Production pack enabled status
Example:
`false`
Was this page helpful?
YesNo
Suggest editsRaise issue
Create Redis DatabaseReset Password
Assistant
Responses are generated using AI and may contain mistakes.
