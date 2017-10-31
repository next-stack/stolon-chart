# Helm chart to install Stolon (HA PostgreSQL cluster)

> Stolon is a cloud native PostgreSQL manager for PostgreSQL high availability.
> It's cloud native because it'll let you keep an high available PostgreSQL inside your containers
> (kubernetes integration) but also on every other kind of infrastructure
> (cloud IaaS, old style infrastructures etc...)

Chart is partially based on the statefullset example from the [stolon repo](https://github.com/sorintlab/stolon/tree/master/examples/kubernetes/statefulset)

Currently only etcd backend is supported.

## Requirements
* Kubernetes >1.5
* PV support on the underlying infrastructure
* Helm 2.2.0 (for `conditions and flags` support)


## TODO:
- [X] Automate initial stolon cluster creating
- [X] Do not manage etcd dependency, do not rely on etcd chart
- [ ] Add support for consul backend
- [X] Add support for 1.6


## Known issues
* etcd from the incubator(and the copy here) has problems with **scale down** and re-joining fallen pods. [#685](https://github.com/kubernetes/charts/issues/685)
