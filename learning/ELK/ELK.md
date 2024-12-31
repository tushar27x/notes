- Elastic Stack
- A set of open source products that have been developed by elastic to help it's users to collect data from different types of sources and then analyze the collected data and represent it in an easy to understand and aesthetic visualization.


ELK consists of 
- [[Elasticsearch]] - It is used storing and searching data
- [[Logstash]] - collecting and filtering data
- [[Kibana]] - used to make visualizations using the stored data.
- [[Beats]] - similar to Logstash, except they are collection of small software that collect data and send it to Elasticsearch.

# ELK Flow

1. Beats attach to remote servers from where the beat collect information from various sources.
2. After collecting the data, it is either shipped to Elasticsearch directly or to Logstash for filtering.
3. After the data has been stored on Elasticsearch, it is not directly sent over to Kibana. Kibana first need to check where Elasticsearch is and then go and get the data itself.

![[7BEA5385-2215-4B0E-AEE3-2345BF44669A.jpeg]]



