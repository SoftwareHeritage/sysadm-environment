/title Deploy next swh version

/milestone %"MRO 2023"

/labels ~"activity::Deployment"

*Note* This proposes a plan to deploy the next swh version. Please, drop the
unneeded actions from the plan.

Actions:
- [ ] Tags all impacted modules

Includes:
- <insert-new-version-packages-with-small-summary>
- ...

Dependency:
- <insert-blocking-dependency>
- ...

staging:
- [ ] storage1.staging: Upgrade package & Restart gunicorn-swh-storage (if storage is impacted)
- [ ] <insert-mr-link> swh-charts: Merge new versions
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment service=<service> service=<service2> ... environment=staging" [1] [2]
- [ ] Checks

production:
- [ ] saam, moma, webapp1: Upgrade swh.storage package & Restart gunicorn-swh-storage (if storage is impacted)
- [ ] swh-charts: Merge staging branch into production
- [ ] Let argocd deploy
- [ ] Tag grafana with "deployment service=<service> service=<service2> ... environment=production" [1] [2]
- [ ] Checks
