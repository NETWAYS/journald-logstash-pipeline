# journald-logstash-pipeline

[![CI](https://github.com/widhalmt/journald-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg?event=push)](https://github.com/widhalmt/journald-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

Minimalist pipeline to fill ECS fields on Beats generated events

* If field `[journald][process][name]` is set and `[process][name]` isn't, the both fields will be created with the same value to restore ECS compatibility.

## Inputs and Outputs ##

If you use files called `input.conf` and `output.conf` they will not collide with this rules, even when you want to pull new versions.

### Examples ###

Here's an example for an `input.conf`

```
input {
  redis {
    host => "localhost"
    data_type => "list"
    key => "netways-journald-input"
  }
}
```

and one for `output.conf`.

```
output {
  redis {
    host => "localhost"
    data_type => "list"
    key => "netways-journald-output"
  }
}
```
