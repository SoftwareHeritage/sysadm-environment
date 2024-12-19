/title Install the new bare metal server(s) for <project>

/labels ~"activity::Deployment"

Orders: <link to the mybox directory containing the order/delivery orders/...>

Installation procedure: https://docs.softwareheritage.org/sysadm/server-architecture/howto-install-new-physical-server.html

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
- [ ] Declare the servers in the [inventory](https://inventory.internal.admin.swh.network)
- [ ] Add the management info in the credential store (root and idrac/ilo access)
- [ ] [Install the OS](https://gitlab.softwareheritage.org/swh/infra/ipxe)
- [ ] (if needed) Add puppet configuration
- [ ] [for kube nodes] Register node in rancher cluster
- [ ] [for kube nodes] Create the required kubernetes labels (e.g. swh/journal_client=true, ...)
- [ ] Create a swap at least the size of the machine's memory
- [ ] Update firewall rules with the new machine's ip (e.g. swh_$environment_kube_workers, ...)
- [ ] (other actions if needed, drop unneeded actions)
