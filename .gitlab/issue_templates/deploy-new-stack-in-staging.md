/title staging: Deploy new <project> stack

/milestone %"Extend archive coverage [Roadmap - Collect]"

/labels ~"activity::Deployment"

*Note* This proposes a plan to deploy the new stack in staging. Please, drop
the unneeded actions from the plan.

- [ ] [swh-apps](https://gitlab.softwareheritage.org/swh/infra/swh-apps/-/tree/master/apps?ref_type=heads): Build image (if required)
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/staging/values-swh-application-versions.yaml?ref_type=heads): Reference new image (if required)
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/production/swh/values/staging/swh-cassandra.yaml#L78): Adapt values to reference the new lister and loaders (if any)
- [ ] Deploy (push staging branch and let argocd do its job)
- [ ] scheduler: Connect to toolbox pod & register new scheduler task types (if required)
- [ ] Tag grafana with "deployment service=loader-<project> service=<lister-project> environment=staging" [1]
- [ ] Checks
  - [ ] pod images are pulled correctly
  - [ ] pods are running without issues (rpc starts, celery workers consume messages, ...)

Dashboard to follow [1]

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

Refs. <issue>
