# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).

## [Unreleased]
### Added
- Per-DeliveryService Routing Names: you can now choose a Delivery Service's Routing Name (rather than a hardcoded "tr" or "edge" name). This might require a few pre-upgrade steps detailed [here](http://traffic-control-cdn.readthedocs.io/en/latest/admin/traffic_ops/migration_from_20_to_22.html#per-deliveryservice-routing-names)
- [Delivery Service Requests](http://traffic-control-cdn.readthedocs.io/en/latest/admin/quick_howto/ds_requests.html#ds-requests): When enabled, delivery service requests are created when ALL users attempt to create, update or delete a delivery service. This allows users with higher level permissions to review delivery service changes for completeness and accuracy before deploying the changes.
- Traffic Ops Golang Proxy Endpoints
  - /api/1.3/about `(GET)`
  - /api/1.3/asns `(GET,POST,PUT,DELETE)`
  - /api/1.3/cachegroups `(GET,POST,PUT,DELETE)`
  - /api/1.3/cdns `(GET,POST,PUT,DELETE)`
  - /api/1.3/cdns/capacity `(GET)`
  - /api/1.3/cdns/configs `(GET)`
  - /api/1.3/cdns/dnsseckeys `(GET)`
  - /api/1.3/cdns/domain `(GET)`
  - /api/1.3/cdns/monitoring `(GET)`
  - /api/1.3/cdns/health `(GET)`
  - /api/1.3/cdns/routing `(GET)`
  - /api/1.3/deliveryservice_requests `(GET,POST,PUT,DELETE)`
  - /api/1.3/divisions `(GET,POST,PUT,DELETE)`
  - /api/1.3/hwinfos `(GET)`
  - /api/1.3/coordinates `(GET,POST,PUT,DELETE)`
  - /api/1.3/login `(POST)`
  - /api/1.3/origins `(GET,POST,PUT,DELETE)`
  - /api/1.3/parameters `(GET,POST,PUT,DELETE)`
  - /api/1.3/profileparameters `(GET,POST,PUT,DELETE)`
  - /api/1.3/phys_locations `(GET,POST,PUT,DELETE)`
  - /api/1.3/ping `(GET)`
  - /api/1.3/profiles `(GET,POST,PUT,DELETE)`
  - /api/1.3/regions `(GET,POST,PUT,DELETE)`
  - /api/1.3/servers `(GET,POST,PUT,DELETE)`
  - /api/1.3/servers/checks `(GET)`
  - /api/1.3/servers/details `(GET)`
  - /api/1.3/servers/status `(GET)`
  - /api/1.3/servers/totals `(GET)`
  - /api/1.3/statuses `(GET,POST,PUT,DELETE)`
  - /api/1.3/system/info `(GET)`
  - /api/1.3/types `(GET,POST,PUT,DELETE)`
- Fair Queuing Pacing: Using the FQ Pacing Rate parameter in Delivery Services allows operators to limit the rate of individual sessions to the edge cache. This feature requires a Trafficserver RPM containing the fq_pacing experimental plugin AND setting 'fq' as the default Linux qdisc in sysctl. 
- Traffic Ops rpm changed to remove world-read permission from configuration files.
- Backup Edge Cache group: If the matched group in the CZF is not available, this list of backup edge cache group configured via Traffic Ops API can be used as backup. In the event of all backup edge cache groups not available, GEO location can be optionally used as further backup. APIs detailed here [here](http://traffic-control-cdn.readthedocs.io/en/latest/development/traffic_ops_api/v12/cachegroup_fallbacks.html)

### Changed
- Reformatted this CHANGELOG file to the keep-a-changelog format

[Unreleased]: https://github.com/apache/incubator-trafficcontrol/compare/RELEASE-2.1.0...HEAD
