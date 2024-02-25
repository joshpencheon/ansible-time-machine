# Time Machine Ansible Playbook

This playbook configures a host for use as a networked Time Machine backup target. It sets up a Samba share for holding backups, and configures Avahi to advertise the share to any macOS clients on the network.

## Using the main playbook

First, set up `inventory.yml` and `vars.yml` files using the provided samples. Assuming you have your host is compatible with Ansible already (has SSH public key installed and has a python interpreter), then run:

```bash
ansible-playbook main.yml
```

## Removing users + backups

If you need to remove users **and data**, a separate playbook is available, which must be invoked with the user to remove:

```bash
ansible-playbook remove_users.yml -e "decomissioned_username=my_old_user"
```

## Further reading

This was inspired by [this article](https://saschaeggi.medium.com/use-a-raspberry-pi-4-for-time-machine-works-with-big-sur-1e66a9650789) by Sascha Eggenberger.
