On this page
EMQX, a robust open-source MQTT message broker, is engineered for scalable, distributed environments, prioritizing high availability, throughput, and minimal latency. As a preferred protocol in the IoT landscape, MQTT (Message Queuing Telemetry Transport) excels in enabling devices to effectively publish and subscribe to messages. Offered by EMQ, EMQX Cloud is a comprehensively managed MQTT service in the cloud, inherently scalable and secure. Its design is particularly advantageous for IoT applications, providing dependable MQTT messaging services. This tutorial guides you on streaming MQTT data to Upstash via data integration. It allows clients to send temperature and humidity data to EMQX Cloud using MQTT and channel it into Upstash for Redis storage.
## 
​
Setting Up Redis Database with Upstash
  1. Log in and create a Redis Database by clicking the **Create Database** button on Upstash Console.
  2. Name your database and select a region close to your EMQX Cloud for optimal performance.
  3. Click **Create** to have your serverless Redis Database ready.


### 
​
Database Details
Access the database console for the necessary information for further steps. The above steps, conclude the initial setup for Upstash.
## 
​
Establishing Data Integration with Upstash
### 
​
Activating EMQX Cloud’s NAT Gateway
  1. Log into the EMQX Cloud console and go to the deployment Overview.
  2. Select **NAT Gateway** at the bottom and click **Subscribe Now**.


### 
​
Configuring Data Integration
  1. In the EMQX Cloud console, choose **Data Integrations** and select **Upstash for Redis**.
  2. Input **Endpoints** info from the Redis detail page into the **Redis Server** field, including the port. Enter the password in **Password** and click **Test** to ensure connectivity. 
  3. Click **New** to add a Redis resource. A new Upstash for Redis will appear under **Configured Resources**.
  4. Formulate a new SQL rule in the **SQL** field. This rule will read from `temp_hum/emqx` and append client_id, topic, timestamp.
     * `up_timestamp`: Message report time
     * `client_id`: Publishing client’s ID
     * `temp`: Temperature data
     * `Hum`: Humidity data


Copy
Ask AI
```
SELECT
timestamp as up_timestamp,
clientid as client_id,
payload.temp as temp,
payload.hum as hum
FROM
"temp_hum/emqx"

```

  5. Execute an SQL test with payload, topic, client info. Successful results confirm the rule’s effectiveness.
  6. Proceed to **Next** to link an action. The rule will store the timestamp, client ID, temperature, and humidity in Redis. Click **Confirm**.
Copy
Ask AI
```
HMSET ${client_id} ${up_timestamp} ${temp}

```

  7. Post-binding, click **View Details** for the rule SQL and bound actions.
  8. To review rules, select **View Created Rules** in Data Integrations. Check detailed metrics in the **Monitor** column.


## 
​
Testing the Data Bridge
  1. Simulate temperature and humidity data with MQTTX. Add connection address and client authentication for the EMQX Dashboard. 
  2. In Upstash Console, under Data Browser, select a client entry to review messages.


Was this page helpful?
YesNo
Suggest editsRaise issue
Replit TemplatesCelery
Assistant
Responses are generated using AI and may contain mistakes.
