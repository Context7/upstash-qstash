On this page
To monitor your Upstash database in Prometheus and visualize metrics in Grafana, follow these steps:
**Integration Scope** Upstash Prometheus Integration only covers Pro databases or those included in the Enterprise Plan.
## 
​
**Step 1: Log in to Your Upstash Account**
  1. Open your web browser and navigate to Upstash.
  2. Navigate to the main dashboard, where you’ll see a list of your databases.


## 
​
**Step 2: Select your Database**
  1. Select the database you want to integrate with Prometheus.
  2. This will open the database settings, where you can manage various configuration options for your selected database.


  3. Enable Prometheus by toggling the switch. This allows you to monitor metrics related to your Upstash database performance, usage, and other key metrics.


## 
​
**Step 3: Connect Accounts**
  1. After enabling Prometheus, a monitoring token is generated and displayed.
  2. Copy this token. This token is unique to your database and is required to authenticate Prometheus with the Upstash metrics endpoint.


**Header Format** You should add monitoring token according to this format `Bearer <MONITORING_TOKEN>`
## 
​
**Step 4: Configure Prometheus to Scrape Upstash Metrics**
  1. Open your Grafana instance, navigate to the Data Sources section, and select Prometheus as the data source.


  2. Enter the data source name, set `https://api.upstash.com/monitoring/prometheus` as the data source address, and then add your monitoring token in the HTTP Header section.


  3. Then, click **Test and Save** to verify that the data source is working properly.


## 
​
**Step 5: Wait for Metrics Availability**
To visualize your Upstash metrics, you can use a pre-built Grafana dashboard. Select your Prometheus data source when prompted, and complete the import. Please check this address to access Upstash Grafana Dashboard  Dashboard 
## 
​
**Conclusion**
You’ve now integrated your database with Upstash Prometheus, providing access to improved monitoring and analytics. Feel free to explore Upstash’s features and dashboards to gain deeper insights into your system’s performance. If you encounter any issues or have questions, please refer to the Upstash support documentation or contact our support team for assistance.
Was this page helpful?
YesNo
Suggest editsRaise issue
DatadogBullMQ
Assistant
Responses are generated using AI and may contain mistakes.
