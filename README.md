# Proxmox setup

Scripted setup to configure a new Proxmox node.

Used in Intel NUC.

## Usage

In your control node (not Proxmox), install Ansible.

```shell
sudo apt install -y sshpass
python3 -m pip install --user --break-system-packages ansible 
```

Copy the file `hosts.template` to `hosts` and update the host list.

Verify you can reach all the hosts.

```shell
ansible all -m ping -i hosts
```

Finally, execute the bootstrapping process.

```shell
ansible-playbook -i hosts bootstrap.yaml
```
