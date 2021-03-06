---
title: Troubleshooting JMX Integrations
kind: faq
---

To verify you have access to JMX, test using JConsole or equivalent if possible. If you're unable to connect using JConsole [this article][1] may help to get you sorted. Also, if the metrics listed in your YAML aren't 1:1 with those listed in JConsole you'll need to correct this.

If you're able to connect using JConsole, run the following:

```
java -jar /opt/datadog-agent/agent/checks/libs/jmxterm-1.0-DATADOG-uber.jar -l localhost:PORT -u USER -p PASSWORD
```

If you're able to connect using the command above run: beans

Send us a copy of the results from above along with:

* [Agent logs][2]
* Output of the [info command][3])
* Output of: ps aux | grep jmxfetch
* /var/log/datadog/jmxfetch.log
* Output of: `sudo /etc/init.d/datadog-agent jmx list_everything`
* A copy of the YAML integration (send the file)

Note, if you're able to see some metrics (`jvm.heap_memory`, `jvm.non_heap_memory`, etc.) it is a sign that JMXFetch is properly running, in this scenario the likely issue is connected to a misconfiguration in your YAML if you're targeting another application.

[1]: https://docs.oracle.com/javase/8/docs/technotes/guides/management/faq.html
[2]: /agent/faq/send-logs-and-configs-to-datadog-via-flare-command
[3]: /agent/faq/agent-status-and-information
