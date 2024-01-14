# Time Machine Ansible Playbook

This playbook configures a host for use as a networked Time Machine backup target. It sets up a Samba share for holding backups, and configures Avahi to advertise the share to any macOS clients on the network.

## Using the playbook

First, set up `inventory.yml` and `vars.yml` files using the provided samples. Assuming you have your host is compatible with Ansible already (has SSH public key installed and has a python interpreter), then run:

```bash
ansible-playbook -i inventory.yml main.yml
```

## Further reading

This was inspired by [this article](https://saschaeggi.medium.com/use-a-raspberry-pi-4-for-time-machine-works-with-big-sur-1e66a9650789) by Sascha Eggenberger.
