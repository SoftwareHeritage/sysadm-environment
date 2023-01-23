/title Decommission node(s) \
/milestone %<milestone>

Inventory: <link to the inventory page>

Summary:
Decommission a node is a multiple process steps which impacts repositories and inventory
references.

Tasks:
- [ ] Update puppet swh-site node references (if any)
- [ ] Actually decomission the node (+ commit/push if within sysadm-provisioning)
- [ ] Update inventory references
  - [ ] delete or deactivate the node(s)
  - [ ] Deprecate or delete the ip addresses
- [ ] Decommission node reference(s) in puppet master `root@pergamon# swh-puppet-master-decommission <node_0> ...<node_n>`
- [ ] <other actions if needed>
