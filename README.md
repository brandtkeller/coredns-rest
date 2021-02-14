# Coredns REST

## Purpose
RESTful API for interacting via CRUD with an associated Coredns Instance.

## Data
There will be no database tied to this application. Rather it will share a data-directory w/ 1 -> N coredns Instances

### Corefile
A single Corefile would be the base.
Incorporating the reload/auto module to trigger changes after modification.
Database files for each zone.

## Deployment

### Static Container
This can be deployed beside a coredns instance on a static compute node with a container engine.

### Kubernetes
This application can be deployed through orchestration to a kubernetes cluster.
Ideally - a ReadWriteMany volume would be shared among the 1 -> N Coredns pods deployed.
A single REST app would then also mount that RWM volume for modifications
