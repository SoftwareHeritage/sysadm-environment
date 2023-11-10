/title staging: Deploy new <project> stack

/milestone %"Extend archive coverage [Roadmap - Collect]"

/labels ~"activity::Deployment"


- [ ] [swh-apps](https://gitlab.softwareheritage.org/swh/infra/swh-apps/-/tree/master/apps?ref_type=heads): Build image (if required)
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/staging/values-swh-application-versions.yaml?ref_type=heads): Reference new image (if required)
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/staging/swh/values/staging.yaml?ref_type=heads#L126): Adapt values to reference the new lister and loader
- [ ] Deploy (push branch and let argocd do its job)
- [ ] Tag grafana with "deployment service=loader-<project> service=<lister-project> environment=staging" [1]
- [ ] Checks pods are doing their jobs

Dashboard to follow [1]

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

Refs. <issue>
