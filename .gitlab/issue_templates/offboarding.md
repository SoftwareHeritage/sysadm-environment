# Summary

***Don't forget to specify the due date if any***

- Name: *Add Name here*

- Gitlab user name: *Add the phabricator username here*

- Matrix login: *if any*

It is hence time to start the offboarding procedure [1]

[1] https://docs.softwareheritage.org/sysadm/user-management/outboarding.html

# Checklist

## Administrative

At the entrance desk, give back:

- [ ] Inria access badge and office keys
- [ ] Cantine card

## Technical setup

- [ ] Lock *nix account on project machines
  - [ ] Edit puppet data for the user
    - [ ] Change password hash to ‘!’ in the swh-private-data repository
    - [ ] Change shell to /bin/false
    - let puppet push itself :)
- [ ] Gitlab: remove user from groups Developers, Members and Interns (if applicable)
- [ ] Revoke VPN certificate
- [ ] Remove “staff” role (and others) from production and staging user accounts on Keycloak

## Development

- [ ] Gitlab: Unassign tasks if any
- [ ] Communication
  - [ ] Unsubscribe from mailing lists: swh-team
  - [ ] Uninvite from Matrix channels: #swh-team

/cc @teams/sysadmin
/confidential
