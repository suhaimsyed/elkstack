## ELK setup

to start the stack type the below at the root folder 

```
docker-compose up
```

Create a logs directory /logstash/logs

Insert the logs at in this directory

## Access Kibana

http://localhost:5601


## Initial setup
Default Kibana index pattern creation
When Kibana launches for the first time, it is not configured with any index pattern.

Via the Kibana web UI
NOTE: You need to inject data into Logstash before being able to configure a Logstash index pattern via the Kibana web UI. Then all you have to do is hit the Create button.

Refer to Connect Kibana with Elasticsearch for detailed instructions about the index pattern configuration.

On the command line
Create an index pattern via the Kibana API:

$ curl -XPOST -D- 'http://localhost:5601/api/saved_objects/index-pattern' \
    -H 'Content-Type: application/json' \
    -H 'kbn-version: 6.4.2' \
    -d '{"attributes":{"title":"logstash-*","timeFieldName":"@timestamp"}}'
The created pattern will automatically be marked as the default index pattern as soon as the Kibana UI is opened for the first time.

