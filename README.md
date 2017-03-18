# Logstash

Basic _logstash_ role.

Defines an ElasticSearch output with indexes specified by `index_name` field, if
no `index_name` is specified, are sent to `undefined` one.

Automatically _inputs_ internal logs with `index_name` *logstash*.

Additional filters should be created in files named `filter-<name>.conf` inside
`/etc/logstash/conf.d` and specifying its `index_name`

## Role Variables

`logstash_elasticsearch_hosts`.

## Dependencies

`oracle-jvm` role.

## Example Playbook

- hosts: servers
  become: yes
  roles:
    - { role: logstash,
        logstash_elasticsearch_hosts: ["192.168.0.1", "192.168.0.2", "192.168.0.3"] }
