# Summary

*more info here if needed*

***Don't forget to specify the due date if any***

Name: *Add Name here*

Phabricator user name: *Add the phabricator username here*

IRC nickname: *if any*

It is hence time to start the offboarding procedure, see https://docs.softwareheritage.org/sysadm/user-management/outboarding.html

# Checklist

## Administrative

At the entrance desk, give back:

- [ ] Inria access badge and office keys
- [ ] cantine card

## Technical setup

- [ ] lock *nix account on project machines
  - [ ] Edit puppet data for the user
    - [ ] Change password hash to ‘!’ in the swh-private-data repository
    - [ ] Change shell to /bin/false
    - let puppet push itself :)
- [ ] phabricator: remove user from groups Developers, Members, - [ ] Interns (if applicable)
  - [ ] revoke VPN certificate
  - [ ] remove “staff” role (and others) from production and staging user accounts on Keycloak

## Development

- [ ] review open and assigned tasks in Phabricator and unassign them as needed.

- [ ] Communication

- [ ] unsubscribe from mailing lists: swh-team
- [ ] uninvite/kick from IRC channels: #swh-team
