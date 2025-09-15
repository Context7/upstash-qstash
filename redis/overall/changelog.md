On this page
​
Feb 2025
Added `EVAL_RO` and `EVALSHA_RO` commands introduced in Redis 7.
​
July 2024
  * Added REST API support for `MONITOR` and `SUBSCRIBE` commands using SSE. See Monitor and Subscribe docs.
  * Added `JSON.MSET` and `JSON.MERGE` commands.
  * Introduced the `IP Allowlist` feature for enhanced security on newly created databases. By default, all IP addresses will be allowed. However, access can be restricted by specifying permitted IP addresses or CIDR ranges.


​
June 2024
  * Added AWS AP-NorthEast-1 Japan region.
  * Added an option to return REST response in `RESP2` format instead of `JSON`. See REST API docs for more information.


​
April 2024
  * Implemented `MONITOR` command
  * Implemented Redis keyspace notifications
  * Implemented `WAIT` and `WAITAOF` commands
  * Added `lag` field to `XINFO GROUPS`
  * Added `CLIENT ID` subcommand
  * Added password strength check to `ACL SETUSER` command


​
February 2024
  * Fixed JSON commands with empty keys
  * Fixed a panic on `XTRIM` and `XDEL`
  * Added `CLIENT SETNAME/NAME/LIST` subcommands
  * Implemented near exact trim for streams


​
September 2023
  * Implemented some missing Redis commands: 
    * `DUMP`
    * `RESTORE`
    * `ZMPOP`
    * `BZMPOP`
    * `LMPOP`
    * `BLMPOP`
    * `SINTERCARD`
  * Added support for `BIT/BYTE` flag to `BITPOS` and `BITCOUNT` commands
  * Added support for `XX`, `NX`, `GT`, and `LT` arguments to `EXPIRE` commands
  * Allowed `NX` and `GET` args to be used together in `SET` command


Was this page helpful?
YesNo
Suggest editsRaise issue
Redis® API CompatibilityUse Cases
Assistant
Responses are generated using AI and may contain mistakes.
