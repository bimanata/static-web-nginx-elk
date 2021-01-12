
## About The Application

This is a simple web application that deploy a static HTML file under web_nginx folder (index.html) and publish it using NGINX as reverse proxy. The web application is dockerize.

This setup also already included with log stream enable using fluentd. And it will stream the log data into elasticsearch, and able to visualize using Kibana.

All this setup and application are docker ready, and already included inside docker-compose file.

Optional approach might be added for backup the log data from elasticsearch, so it will be persistent. The approach are using S3 plugin and Terraform script also added inside the code folder.

## How To Run The Application

1. Run Docker using docker-compose
   ```sh
   docker-compose up
   ```

3. Once the container is running, you can use this url to connect with the application.

* Static Web : http://localhost:80
* Elasticsearch : http://localhost:9200
* Kibana : http://localhost:5601

4. Open the static website numerous time or using curl command, so it will produce log and fluentd will stream the logs to elasticsearch

5. Open Kibana and add index 'fluentd-*' to show it on Discover
