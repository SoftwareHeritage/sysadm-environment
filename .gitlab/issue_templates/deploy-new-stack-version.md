/title Deploy new <project> <version>

/milestone %<milestone>

/label ~"activity::deployment"

staging:
- [ ] [swh-apps](https://gitlab.softwareheritage.org/swh/infra/swh-apps/-/tree/master/apps?ref_type=heads): Build image (if required because of new deps for example)
- [ ] [swh-charts](https://gitlab.softwareheritage.org/swh/infra/ci-cd/swh-charts/-/merge_requests): Merge MR with image versions updates triggered by the CI
- [ ] Push branch 'staging' && Let argocd deploy and do its job
- [ ] Checks pods are doing their jobs without crashing
- [ ] Tag grafana with "deployment service=<service> service=<service2> ... environment=staging" [1] [2]

production:
- [ ] Merge 'staging' branch into 'production' (it should/must be a fast-forward)
- [ ] Push branch 'production' && Let argocd deploy and do its job
- [ ] Tag grafana with "deployment service=<service> service=<service2> ... environment=production" [1] [2]
- [ ] Checks pods are doing their jobs without crashing

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

[2] Only reference impacted services (e.g. storage, lister-cran, loader-git, scheduler, vault, ...)

Refs. <issue>
