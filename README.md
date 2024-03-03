# Elastic stack (ELK) on Docker for opnsense
This repository shows how to deploy the ELK stack and configure OPNsense and to send `syslogs` and `NetFlow Records` to it.

## Credits

[deviantony/docker-elk](https://github.com/deviantony/docker-elk)

---

## Quickstart

1. Change the passwords in the `.env` file.
2. `docker compose up setup`
3. `docker compose up -d`.
4. Give Kibana about a minute to initialize
5. Configure the ELK stack integrations as documented [here](doc/integrations.md)
6. Configure the OPNsense as documented [here](doc/opnsense.md).
7. Go to the `Dashboards` section in `Kibana` and you will find pre-built dashboards that come with the implemented ELK integrations

By default, the stack exposes the following ports:

* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5601: Kibana
* 9001: pfsense integration UDP
* 2055: netflow integration UDP


> [!WARNING]
> Elasticsearch's [bootstrap checks][bootstrap-checks] were purposely disabled to facilitate the setup of the Elastic
> stack in development environments. For production setups, we recommend users to set up their host according to the
> instructions from the Elasticsearch documentation: [Important System Configuration][es-sys-config].

For the extended documentation please visit [deviantony/docker-elk](https://github.com/deviantony/docker-elk)