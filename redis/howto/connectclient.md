On this page
Upstash works with Redis® API, that means you can use any Redis client with Upstash. At the Redis Clients page you can find the list of Redis clients in different languages. Probably, the easiest way to connect to your database is to use `redis-cli`. Because it is already covered in Getting Started, we will skip it here.
## 
​
Database
After completing the getting started guide, you will see the database page as below:
The information required for Redis clients is displayed here as **Endpoint** , **Port** and **Password**. Also when you click on `Clipboard` button on **Connect to your database** section, you can copy the code that is required for your client. Below, we will provide examples from popular Redis clients, but the information above should help you configure all Redis clients similarly.
TLS is enabled by default for all Upstash Redis databases. It’s not possible to disable it.
## 
​
upstash-redis
Because upstash-redis is HTTP based, we recommend it for Serverless functions. Other TCP based clients can cause connection problems in highly concurrent use cases.
**Library** : upstash-redis **Example** :
Copy
Ask AI
```
import { Redis } from '@upstash/redis';

const redis = new Redis({ url: 'UPSTASH_REDIS_REST_URL', token: 'UPSTASH_REDIS_REST_TOKEN' });

(async () => {
  try {
    const data = await redis.get('key');
    console.log(data);
  } catch (error) {
    console.error(error);
  }
})();

```

## 
​
Node.js
**Library** : ioredis **Example** :
Copy
Ask AI
```
const Redis = require("ioredis");

let client = new Redis("rediss://:YOUR_PASSWORD@YOUR_ENDPOINT:YOUR_PORT");
await client.set("foo", "bar");
let x = await client.get("foo");
console.log(x);

```

## 
​
Python
**Library** : redis-py **Example** :
Copy
Ask AI
```
import redis
r = redis.Redis(
host= 'YOUR_ENDPOINT',
port= 'YOUR_PORT',
password= 'YOUR_PASSWORD', 
ssl=True)
r.set('foo','bar')
print(r.get('foo'))

```

## 
​
Java
**Library** : jedis **Example** :
Copy
Ask AI
```
Jedis jedis = new Jedis("YOUR_ENDPOINT", "YOUR_PORT", true);
jedis.auth("YOUR_PASSWORD");
jedis.set("foo", "bar");
String value = jedis.get("foo");
System.out.println(value);

```

## 
​
Go
**Library** : redigo **Example** :
Copy
Ask AI
```
func main() {
  c, err := redis.Dial("tcp", "YOUR_ENDPOINT:YOUR_PORT", redis.DialUseTLS(true))
  if err != nil {
      panic(err)
  }

  _, err = c.Do("AUTH", "YOUR_PASSWORD")
  if err != nil {
      panic(err)
  }

  _, err = c.Do("SET", "foo", "bar")
  if err != nil {
      panic(err)
  }

  value, err := redis.String(c.Do("GET", "foo"))
  if err != nil {
      panic(err)
  }

  println(value)
}

```

Was this page helpful?
YesNo
Suggest editsRaise issue
Ratelimiting AlgorithmsConnect with upstash-redis
Assistant
Responses are generated using AI and may contain mistakes.
