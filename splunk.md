- exploring the available log sources in Splunk. The initial query used is

```
| metadata type=sourcetypes | dedup sourcetype | table sourcetype
```

This query helps list all the sourcetypes present in the Splunk environment, allowing us to identify which log sources are available for analysis. The metadata command retrieves metadata information about the indexed data, while dedup sourcetype ensures that duplicate sourcetype entries are removed. Finally, table sourcetype formats the output into a clear, readable table showing the different log types.

- Suricata is a network threat detection engine that logs suspicious activities such as intrusion attempts and malware downloads.

Focusing on the suricata logs, we need to examine HTTP-related events because the suspicious activity involves downloading an executable file. The query used for this is

```
sourcetype="suricata" event_type="http" 
| stats values(http.http_user_agent) as user_agents, values(http.url) as urls, values(src_ip) as server by dest_ip
```

This search filters the logs to include only HTTP events, as indicated by event_type="http". The stats command is then employed to aggregate and organize the data. Specifically, it collects distinct values of http.http_user_agent under the alias user_agents, http.url under urls, and src_ip under server, grouping these details by dest_ip. This structured output allows us to easily identify which external IP addresses interacted with the network, what files or resources were accessed, and the user agents used in these interactions.

modified querry for executable downloads:

```
sourcetype="suricata" event_type="http" AND http.url="*.exe" 
| stats values(http.http_user_agent) as user_agents, values(http.url) as urls, values(src_ip) as server by dest_ip
```

To begin, we search for DNS queries related to the IP address 195.88.191.59, which was previously identified as the origin of the attack. The query used in Splunk is

```
sourcetype="zeek:dns" AND "195.88.191.59"
```

This query filters the DNS logs captured by Zeek, an open-source network analysis tool that monitors and logs DNS traffic, among other network activities. The sourcetype="zeek:dns" specifies that only DNS-related logs are considered, while the IP address ensures that we only retrieve DNS activity related to the attacker.