# coseismic_usgs_neic
USGS NEIC scraper query

This repository contains the USGS National Earthquake Information Center (NEIC) scraper which polls the service via cron and ingests any earthquakes that pass the filter criteria. The cron runs every 15 minutes by default.

## Build Instructions

Built using the ARIA HySDS Jenkins Continuous Integration (CI) pipeline.

More information about this process can be found [here](https://hysds-core.atlassian.net/wiki/spaces/HYS/pages/455114757/Deploy+PGE+s+onto+Cluster)

Within the ARIA production environment, this PGE is built using the ARIA Jenkins server. You'll want to log onto the ARIA Mozart server and add / watch this repo first, then open up the Jenkins server in a browser and navigate to the project for this repo (which should show up after adding / watching this repo via the `sds ci ...` commands documented in the above link)

## Run Instructions

You may run your customized PGE via two methods that are documented below:
- An [on-demand (one-time) job](https://hysds-core.atlassian.net/wiki/spaces/HYS/pages/378601499/Submit+an+On-Demand+Job+in+Facet+Search)
- [Create a trigger rule](https://hysds-core.atlassian.net/wiki/spaces/HYS/pages/442728660/Create+Edit+Delete+Trigger+Rules) to invoke your PGE based on conditions

### USGS NEIC scraper query

The minimum magnitude for events to ingest is set to 2.5.
```
submit_neic_query.py --minmag 2.5 --updated_since redis
```

## Release History

`v1.0.0` - 

## Contributing

1. Create an GitHub issue ticket describing what changes you need (e.g. issue-1)
2. Fork this repo (<https://github.com/aria-jpl/coseismic_usgs_neic/fork>)
3. Make your modifications in your own fork
4. Make a pull-request in this repo with the code in your fork and tag the repo owner / largest contributor as a reviewer

## Support

Contact `@mlucas` for support.


