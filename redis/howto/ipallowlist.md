On this page
IP Allowlist is available on all plans except for the free plan.
IP Allowlist can be used to restrict which IP addresses are permitted to access your database by comparing a connection’s address with predefined CIDR blocks. This feature enhances database security by allowing connections only from specified IP addresses. For example if you have dedicated production servers with static IP addresses, enabling IP allowlist blocks connections from other addresses.
## 
​
Enabling IP Allowlist
By default, any IP address can be used to connect to your database. You must add at least one IP range to enable the allowlist. You can manage added IP ranges in the `Configuration` section on the database details page. You can either provide
  * IPv4 address, e.g. `37.237.15.43`
  * CIDR block, e.g. `181.49.172.0/24`


Currently, IP Allowlist only supports IPv4 addresses.
You can use more than one range to allow multiple clients. Meeting the criteria of just one is enough to establish a connection.
It may take a few minutes for changes to propagate.
Was this page helpful?
YesNo
Suggest editsRaise issue
Listen Keyspace NotificationsRead Your Writes
Assistant
Responses are generated using AI and may contain mistakes.
