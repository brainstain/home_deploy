# Deploy a cluster with ansible
1) setup the hardware and move an ssh key to each node.  details forthcoming (update hostname, move ssh key)
2) setup the inventory file (hosts is an example)
3) set local envs for the following:

```
export datastore_endpoint='--datastore-endpoint="<connection info to db if using for etcd>"'
export token='<existing token for cluster if applicable>'
```
4) run the ansible script:
```
ansible-playbook -i hosts -e "datastore_endpoint=$datastore_endpoint token=$token" -b pbook.yaml
```


##note
add this:
sudo rm -f /etc/resolv.conf
sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf