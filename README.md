# Kibana-Vega-Visualizations
#### DNS subdomain_length Scatter Plot
This visualization will display the outliers for the subdomain_lenght field and sperate them by the query type.  It can be used to detect DNS tunneling techniques from tools such as iodine where the attacker will base64 encode or encrypt the data they want to exfiltrate, slice it, then add it as the subdomin of a dns query. 
Notes:
1. By default, Elasticsearch will only return a max of 10000 results. So depending on the volume of DNS queries you may consider adding filters when you build the visuilazation to reduce the number of retunred values.  Below is an example query:
  **event_type:bro_dns AND subdomain_length: [20 TO * ]**
2. If you are running the frequency server docker container you can also display the frequency score of the subdomain and display that score in a scatter plot.
