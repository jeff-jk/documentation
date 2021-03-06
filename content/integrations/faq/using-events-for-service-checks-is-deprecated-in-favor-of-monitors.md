---
title: Service checks is deprecated in favor of monitors
kind: faq
---

Iy your are seeing this message:
```
Instance #0[WARNING]: Using events for service checks is deprecated in favor of monitors and will be removed in future versions of the Datadog Agent.
```

The Datadog 5.x agent introduced a new method for reporting on various states via Monitors versus the old method which relied on Events.

The warning is innocuous and it is intended to notify customers who are relying exclusively on Events that there are new notification methods that should be used moving forward.

If this warning is a distraction for you or your team you may get rid of it by enabling the “skip_event” attribute in the source YAML file. [Here is an example][1] using the HTTP_check:

[1]: https://github.com/DataDog/integrations-core/blob/master/http_check/conf.yaml.example#L110-L114
