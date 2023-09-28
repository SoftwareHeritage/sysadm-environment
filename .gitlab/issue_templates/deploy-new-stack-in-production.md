/title production: Deploy new <project> stack

/milestone %<milestone>

/label ~"activity::deployment"

- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/production/swh/values/production.yaml?ref_type=heads#L126): Checkout production branch
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/production/swh/values/production.yaml?ref_type=heads#L143): Adapt values to reference the new lister and loader (equivalent to what was done for staging)
- [ ] Deploy (push branch and let argocd do its job)
- [ ] Tag grafana with "deployment service=loader-<project> service=<lister-project> environment=production" [1]
- [ ] Checks pods are doing their jobs

Dashboard to follow [1]

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

Refs. <issue>
