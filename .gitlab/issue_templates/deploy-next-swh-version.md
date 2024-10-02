/labels ~"activity::Deployment"

*Note* This proposes a plan to deploy the next swh version. Note that we usually
manually name the issue "Deploy next swh version $version". Prior to actually create the
issue, drop the unneeded actions from the plan.

Actions:
- [ ] Tags all impacted modules

Includes:
- $insert-new-version-packages-with-small-summary$
- ...

Dependency:
- $insert-blocking-dependency-if-any$
- ...

staging:
- [ ] $insert-mr-link$: swh-charts: Merge new version(s)
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment environment=staging service=$service1$ service=$service2$"
- [ ] Checks
  - [ ] Check model version upgrade if any (e.g. webapp, scheduler, storage primary, storage secondary replica, ...)
  - [ ] Check pod images are pulled correctly
  - [ ] Check pods are running without issues (rpc starts, celery workers consume messages, ...)

production:
- [ ] swh-charts: Merge staging branch into production
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment environment=production service=$service1$ service=$service2$"
- [ ] Checks
  - [ ] Check model version upgrade if any (e.g. webapp, scheduler, storage primary, storage secondary replica, ...)
  - [ ] Check pod images are pulled correctly
  - [ ] Check pods are running without issues (rpc starts, celery workers consume messages, ...)
