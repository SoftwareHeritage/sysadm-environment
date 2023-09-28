/title Deploy new <project> stack in staging

/milestone %<milestone>

/label ~"activity::deployment"

- [ ] swh-apps: Build image (if required)
- [ ] swh-charts: Reference new image (if required)
- [ ] swh-charts: Adapt values to reference the new lister and loader
- [ ] Deploy
- [ ] Checks

Dashboard to follow [1]

[1] https://grafana.softwareheritage.org/goto/e-c3EAWIz?orgId=1

Refs. <issue>
