# journald-logstash-pipeline

[![CI](https://github.com/widhalmt/journald-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg?event=push)](https://github.com/widhalmt/journald-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

Minimalist pipeline to fill ECS fields on Beats generated events

* If field `[journald][process][name]` is set and `[process][name]` isn't, the both fields will be created with the same value to restore ECS compatibility.
