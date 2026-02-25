This folder contains the centralized renovate configuration file.
It's expected to be used by a cronjob running inside the admin cluster in the swh infra.

# Summary
Renovate is an automated dependency update tool. It helps to update dependencies in your 
code without needing to do it manually. When Renovate runs on a repo, it looks for references 
to dependencies (both public and private) and, if there are newer versions available, 
Renovate can create pull requests to update your versions automatically.

# Currently
Only the dockerfile manager is enabled.
Enable more managers manually if needed. [1]

[1] https://docs.renovatebot.com/modules/manager/ 
