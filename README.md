## Description

Automatically send pm2 monit stasts to Elasticsearch

![Kibana Dashboard](https://github.com/liquid36/pm2-monit-elk/blob/master/kibana-dashboard.png "Kibana Dashboard")

# pm2-monit-elk

## Install

```bash
$ npm install pm2 -g

$ pm2 install pm2-monit-elk
```

## Configuration

Default settings:

* `interval` is `10` second. Represents the refresh_rate of the cpu and network workers.
* `elasticsearch_url` is `localhost:9200`. Represents Elasticsearch host URL.
* `elasticsearch_index` is `server_monitoring`. Represents index to save server monitoring logs in Elasticsearch.
* `elasticsearch_user` is blank by default.
* `elasticsearch_password` is blank by default.

To modify the config values you can use Keymetrics dashboard or the following commands:

```bash
pm2 set pm2-monit-elk:interval 2
pm2 set pm2-monit-elk:elasticsearch_url es.example.com:9200
pm2 set pm2-monit-elk:elasticsearch_index server_monitoring_new
pm2 set pm2-monit-elk:elasticsearch_user username
pm2 set pm2-monit-elk:elasticsearch_password password
```

NOTE: If basic authentication is enabled on your elasticsearch, specially via Search Guard, provide username and password as part of host url e.g. "http://username:pass@localhost:9200"

:warning: If this module uses too much CPU, set the `interval` value to 10 or more.

## Uninstall

```bash
$ pm2 uninstall pm2-monit-elk
```

## Update to latest version

```bash
$ pm2 module:update pm2-monit-elk
```

# License

MIT


# Thanks
Thnaks to  @jokerguys and his repository https://github.com/jokerguys/pm2-server-monit-elasticsearch for some ideas.
