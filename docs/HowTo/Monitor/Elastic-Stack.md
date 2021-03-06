description: Using Elastick Stack (ELK) with Hyperledger Besu
<!--- END of page meta data -->

# Elastic Stack 

Elastic Stack (also known as ELK) is a common open-source log management platform. 

The [Besu Quickstart](https://github.com/PegaSysEng/besu-quickstart) provides an example implementation 
using Elastic Stack for log management. 

The [Filebeat configuration](https://github.com/PegaSysEng/besu-quickstart/blob/master/filebeat/filebeat.yml)
ingests the logs and outputs them to Redis for storage. Redis provides a highly available mechanism that 
enables logs to be stored by any of the Elastic Beats and pulled by Logstash as required. 

The [pipeline configuration](https://github.com/PegaSysEng/besu-quickstart/blob/master/logstash/pipeline/20_besu.conf) 
defines the json format used for Besu logs and automatically picks up any new log fields. 

!!! note
    The pipeline configuration must match the your log format. If using the default, you can use the 
    [grok plugin](https://www.elastic.co/guide/en/logstash/current/plugins-filters-grok.html) to 
    extract the log fields. 

To see the Besu Quickstart logs in Kibana:  

1. [Start the Besu Quickstart](../../Tutorials/Quickstarts/Private-Network-Quickstart.md).
1. Open the [`Kibana logs address`](http://localhost:5601/app/kibana#/discover) listed by the Besu Quickstart. 
   The logs are displayed in Kibana. 
   
    ![Kibana](../../images/KibanaQuickstart.png)

