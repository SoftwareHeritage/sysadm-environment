/title Recycle old bare metal server(s) into a rancher node for <project>

/labels ~"activity::Deployment"

Orders: <link to the mybox directory containing the order/delivery orders/...>

Inventory: <link to the inventory page>

Environment: admin|production|staging|test-staging

Summary:
- Management address (DNS): XXX.XXX.XXX.XXX (abcd.inria.fr)
- VLAN configuration: VLANXXXX/VLANXXX
- Management Port:
- Access Ports:
- Internal IP(s): xxx.xxx.xxx.xxx
- Internal DNS name(s): xxx.internal.(softwareheritage.org|`<environment>`.swh.network

Tasks:
- [ ] Decommission `old-fqdn` on pergamon
- [ ] Remove `<old-fqdn>.yaml` from the puppet repository
- [ ] Update the node's information in the inventory
- [ ] Create `<new-fqdn>.yaml` in the puppet repository
- [ ] Reinstall Debian bullseye with IPXE
- [ ] Register the new node in the cluster `<target-environment-cluster>`
- [ ] Create the required kubernetes labels (e.g. swh/journal_client=true, ...)
- [ ] Create a swap at least the size of the machine's memory
- [ ] Update firewall rules with the new machine's ip (e.g. swh_$environment_kube_workers, ...)
- [ ] (other actions if needed, drop unneeded actions)

