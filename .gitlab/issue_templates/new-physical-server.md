/title Install the new bare metal server(s) for <project>

/milestone %"MRO 2023"

/labels ~"activity::Deployment"

Orders: <link to the mybox directory containing the order/delivery orders/...>

Inventory: <link to the inventory page>

Summary:
- Management address (DNS): XXX.XXX.XXX.XXX (abcd.inria.fr)
- VLAN configuration: VLANXXXX/VLANXXX
- Management Port:
- Access Ports:
- Internal IP(s): xxx.xxx.xxx.xxx
- Internal DNS name(s): xxx.internal.(softwareheritage.org|<environment>.swh.network

Tasks:
- [ ] Declare the servers in the [inventory](https://inventory.internal.admin.swh.network)
- [ ] Add the management info in the credential store
- [ ] Install the OS
- [ ] Add puppet configuration (if needed)
- [ ] Configure firewall rules (if needed)
- [ ] (other actions if needed, drop unneeded actions)
