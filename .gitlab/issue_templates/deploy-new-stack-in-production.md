/title production: Deploy new <project> stack

/milestone %"Extend archive coverage [Roadmap - Collect]"

/labels ~"activity::Deployment"

*Note* This proposes a plan to deploy the new stack in production. Please,
drop the unneeded actions from the plan.

production:
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/production/swh/values/production/swh.yaml#L501): Checkout staging branch, adapt values to reference the new lister and loaders (if any)
- [ ] Checkout production branch and merge staging branch (they should be aligned)
- [ ] Deploy (push production branch and let argocd do its job)
- [ ] scheduler: Connect to toolbox pod & register new scheduler task types (if required)
- [ ] Tag grafana with "deployment service=loader-<project> service=<lister-project> environment=staging" [1]
- [ ] Checks
  - [ ] pod images are pulled correctly
  - [ ] pods are running without issues (rpc starts, celery workers consume messages, ...)


Dashboard to follow [1]

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

Refs. <issue>
