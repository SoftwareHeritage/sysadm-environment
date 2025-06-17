/labels ~"activity::MRO"

staging:
- [ ] client: They need to create their account in the staging keycloak realm
- [ ] client: `client-login`
- [ ] Awaiting domain and provider url from client: `<ask-client>`
- [ ] Add `swh.deposit.api` role to user in keycloak in staging realm
- [ ] deposit db: Create deposit api collection & client [2] (requires domain and provider url first)
- [ ] Ask client whether the deposit access is ok

production:
- [ ] client: They need to create their account in the production keycloak realm
- [ ] client: `client-login`
- [ ] Awaiting domain and provider url from client: `<ask-client>`
- [ ] Add `swh.deposit.api` role to user in keycloak in production realm
- [ ] deposit db: Create deposit api collection & client [2] (same as staging)
- [ ] Ask client whether the deposit access is ok

[1] https://docs.softwareheritage.org/devel/swh-deposit/api/register-account.html#as-a-sysadm

[2] Output sample cli
```
swhdeposit@deposit:~$ swh deposit admin \
  --config-file $SWH_CONFIG_FILENAME \
  --platform production \
  user create \
    --collection "<collection>" \
    --username "<username>" \
    --provider-url <url-tbd> \
    --domain "<domain>"
Collection '<collection>' exists, skipping.
Create user '<username>'.
User '<username>' created.
```
