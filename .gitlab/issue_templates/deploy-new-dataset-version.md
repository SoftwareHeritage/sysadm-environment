/labels ~"activity::Deployment"

The documentation for this deployment is documented [1]

[1] https://docs.softwareheritage.org/sysadm/deployment/howto-generate-compressed-graph-dataset.html

# Actions
- [ ] Are impacted modules tagged (swh.graph, swh.dataset, swh.export)?

# Includes
- swh.graph vx.y.z: $insert-small-summary$
- swh.dataset vx.y.z: $insert-small-summary$
- swh.export vx.y.z: $insert-small-summary$

# Dependency
- $insert-blocking-dependency-issue-if-any$
- ...

# staging
- [ ] $insert-mr-link-swh-charts$: next-version: Adapt the pinned version of
      the datasetsGenerator.image to use the new version [2]
- [ ] $insert-mr-link-swh-charts$: next-version: Merge new version(s) in staging branch
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment environment=staging service=dataset"
- [ ] Checks
  - [ ] Check pod images are pulled correctly (e.g. "dataset-", "luigi-scheduler-")
  - [ ] Check pods are running without issues (no crashloop)

# production
- [ ] swh-charts: Merge staging branch into production (adapt the pinned
      version if not done already)
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment environment=production service=dataset"
- [ ] Checks
  - [ ] Check pod images are pulled correctly (e.g. "dataset-", "luigi-scheduler-")
  - [ ] Check pods are running without issues (no crashloop)

[2] https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/blob/production/swh/values.yaml?ref_type=heads#L2160
