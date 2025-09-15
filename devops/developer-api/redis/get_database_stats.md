Get Database Stats
cURL
Copy
Ask AI
```
curl --request GET \
  --url https://api.upstash.com/v2/redis/stats/{id} \
  --header 'Authorization: Basic <encoded-value>'
```

200
Copy
Ask AI
```
{
  "monitor_count": {
    "x": "2023-05-22 10:59:23.426 +0000 UTC",
    "y": 320
  },
  "daily_net_commands": 7,
  "daily_read_requests": 7,
  "daily_write_requests": 0,
  "connection_count": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "keyspace": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "throughput": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "diskusage": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "latencymean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read_latency_mean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read_latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write_latency_mean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write_latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "hits": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "misses": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "dailyrequests": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 7
    }
  ],
  "days": [
    "Sunday",
    "Monday",
    "Tuesday",
    "Wednesday",
    "Thursday"
  ],
  "dailybilling": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 1.333
    }
  ],
  "dailybandwidth": 50444740913,
  "bandwidths": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 7
    }
  ],
  "total_monthly_bandwidth": 7,
  "total_monthly_requests": 7,
  "total_monthly_read_requests": 7,
  "total_monthly_write_requests": 0,
  "total_monthly_script_requests": 0,
  "queue_optimized": false,
  "total_monthly_storage": 0,
  "current_storage": 0,
  "total_monthly_billing": 222.33902763855485,
  "command_counts": [
    {
      "metric_identifier": "EXISTS",
      "data_points": [
        {
          "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
          "y": 0
        }
      ]
    }
  ]
}
```

GET
/
redis
/
stats
/
{id}
Try it
Get Database Stats
cURL
Copy
Ask AI
```
curl --request GET \
  --url https://api.upstash.com/v2/redis/stats/{id} \
  --header 'Authorization: Basic <encoded-value>'
```

200
Copy
Ask AI
```
{
  "monitor_count": {
    "x": "2023-05-22 10:59:23.426 +0000 UTC",
    "y": 320
  },
  "daily_net_commands": 7,
  "daily_read_requests": 7,
  "daily_write_requests": 0,
  "connection_count": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "keyspace": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "throughput": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "diskusage": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "latencymean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read_latency_mean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read_latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write_latency_mean": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write_latency_99": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "hits": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "misses": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "read": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "write": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    }
  ],
  "dailyrequests": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 7
    }
  ],
  "days": [
    "Sunday",
    "Monday",
    "Tuesday",
    "Wednesday",
    "Thursday"
  ],
  "dailybilling": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 1.333
    }
  ],
  "dailybandwidth": 50444740913,
  "bandwidths": [
    {
      "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
      "y": 0
    },
    {
      "x": "2025-09-04 15:12:52.76649148 +0000 UTC",
      "y": 7
    }
  ],
  "total_monthly_bandwidth": 7,
  "total_monthly_requests": 7,
  "total_monthly_read_requests": 7,
  "total_monthly_write_requests": 0,
  "total_monthly_script_requests": 0,
  "queue_optimized": false,
  "total_monthly_storage": 0,
  "current_storage": 0,
  "total_monthly_billing": 222.33902763855485,
  "command_counts": [
    {
      "metric_identifier": "EXISTS",
      "data_points": [
        {
          "x": "2025-08-31 15:12:52.799480932 +0000 UTC",
          "y": 0
        }
      ]
    }
  ]
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
The ID of the database
#### Response
200 - application/json
Database stats retrieved successfully
​
monitor_count
object
Monitor count
Show child attributes
​
daily_net_commands
integer
Total number of commands executed today
Example:
`7`
​
daily_read_requests
integer
Total number of read requests executed today
Example:
`7`
​
daily_write_requests
integer
Total number of write requests executed today
Example:
`0`
​
connection_count
object[]
Connection count over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
keyspace
object[]
Total number of keys in the database over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
throughput
object[]
Throughput on database connections over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
diskusage
object[]
Disk usage over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
latencymean
object[]
Average latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
latency_99
object[]
99th percentile latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
read_latency_mean
object[]
Average read latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
read_latency_99
object[]
99th percentile read latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
write_latency_mean
object[]
Average write latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
write_latency_99
object[]
99th percentile write latency over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
hits
object[]
Cache hits over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
misses
object[]
Cache misses over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
read
object[]
Read requests over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
write
object[]
Write requests over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  }  
]
```

​
dailyrequests
object[]
Daily requests over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  },  
  {  
    "x": "2025-09-04 15:12:52.76649148 +0000 UTC",  
    "y": 7  
  }  
]
```

​
days
string[]
Days of the week for measurement
Example:
```
[  
  "Sunday",  
  "Monday",  
  "Tuesday",  
  "Wednesday",  
  "Thursday"  
]
```

​
dailybilling
object[]
Daily billing amounts over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  },  
  {  
    "x": "2025-09-04 15:12:52.76649148 +0000 UTC",  
    "y": 1.333  
  }  
]
```

​
dailybandwidth
integer
Total daily bandwidth usage in bytes
Example:
`50444740913`
​
bandwidths
object[]
Bandwidth usage over time
Show child attributes
Example:
```
[  
  {  
    "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
    "y": 0  
  },  
  {  
    "x": "2025-09-04 15:12:52.76649148 +0000 UTC",  
    "y": 7  
  }  
]
```

​
total_monthly_bandwidth
integer
Total bandwidth used in current month (bytes)
Example:
`7`
​
total_monthly_requests
integer
Total requests in current month
Example:
`7`
​
total_monthly_read_requests
integer
Total read requests in current month
Example:
`7`
​
total_monthly_write_requests
integer
Total write requests in current month
Example:
`0`
​
total_monthly_script_requests
integer
Total script requests in current month
Example:
`0`
​
queue_optimized
boolean
Whether queue optimization is enabled for the database
Example:
`false`
​
total_monthly_storage
integer
Total storage used in current month (bytes)
Example:
`0`
​
current_storage
integer
Current storage used (bytes)
Example:
`0`
​
total_monthly_billing
number
Total cost in current month
Example:
`222.33902763855485`
​
command_counts
object[]
Command-specific counts over time
Show child attributes
Example:
```
[  
  {  
    "metric_identifier": "EXISTS",  
    "data_points": [  
      {  
        "x": "2025-08-31 15:12:52.799480932 +0000 UTC",  
        "y": 0  
      }  
    ]  
  }  
]
```

Was this page helpful?
YesNo
Suggest editsRaise issue
Get DatabaseCreate Redis Database
Assistant
Responses are generated using AI and may contain mistakes.
