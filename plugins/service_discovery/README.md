# Service Discovery Plugin Overview

Fluentd has 8 types of plugins: [Input](/plugins/input/README.md),
[Parser](/plugins/parser/README.md), [Filter](/plugins/filter/README.md),
[Output](/plugins/output/README.md),
[Formatter](/plugins/formatter/README.md),
[Storage](/plugins/storage/README.md),
[Service Discovery](/plugins/service_discovery/README.md) and [Buffer](/plugins/buffer/README.md).
This article gives an overview of Service Discovery Plugin.

## Overview

Some of the plugins has the `<service_discovery>` (ex: [out\_forward](/plugins/output/forward.md)).
Sometimes, the service discovery for an output plugin doesn't meet one's
needs. Fluentd has a pluggable system called Service Discovery that lets the
user extend and re-use custom output service discovery.


## How To Use

Here is a simple example to update target by reading file(`/etc/fluentd/sd.yaml`) with `out_forward` and
`service_discovery`:

```
<source>
  @type forward

  <service_discovery>
    @type file
     path "/etc/fluentd/sd.yaml"
  </service_discovery>
</source>
```


## List of Built-in Service Discovery

-   [static](/plugins/service_discovery/static.md)
-   [file](/plugins/service_discovery/file.md)

## List of Core Input Plugins with Parser support

with `<service_discovery>` directive.

-   [out\_forward](/plugins/output/forward.md)

------------------------------------------------------------------------

If this article is incorrect or outdated, or omits critical information, please [let us know](https://github.com/fluent/fluentd-docs-gitbook/issues?state=open).
[Fluentd](http://www.fluentd.org/) is a open source project under [Cloud Native Computing Foundation (CNCF)](https://cncf.io/). All components are available under the Apache 2 License.