/labels ~"activity::MRO"

The following actions must be executed in order per environment.

staging:
- [ ] client: They need to create their account in the staging keycloak realm
- [ ] Ask client for the following information:
  - login: `<edit-client-login-when-known>`
  - collection: it's the same as the login
  - domain: `<edit-domain-when-known>`
  - provider_url: `<edit-domain-when-known>`
- [ ] Add `swh.deposit.api` role to user in keycloak in staging realm
- [ ] deposit db: Create deposit api collection & client [2]
- [ ] Ask client whether the deposit access is ok

production:
- [ ] client: They need to create their account in the production keycloak realm
- [ ] Ask client for the following information:
  - login: `<edit-client-login-when-known>`
  - collection: it's the same as the login
  - domain: `<edit-domain-when-known>`
  - provider_url: `<edit-domain-when-known>`
- [ ] Add `swh.deposit.api` role to user in keycloak in production realm
- [ ] deposit db: Create deposit api collection & client [2]
- [ ] Ask client whether the deposit access is ok

[1] https://docs.softwareheritage.org/devel/swh-deposit/api/register-account.html#as-a-sysadm

[2] Example sample cli to adapt accordingly and execute
```
username=<replace>
collection_name=$username
provider_url=<replace>
domain=<replace>
swh deposit admin \
  --config-file $SWH_CONFIG_FILENAME \
  --platform production \
  user create \
    --collection "${collection_name}" \
    --username "${username}" \
    --provider-url "${provider_url}" \
    --domain "${domain}"
```
