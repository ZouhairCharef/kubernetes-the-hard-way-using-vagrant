# Prerequisites

## K8S Cluster Architecture

![image](https://user-images.githubusercontent.com/38728584/235473544-2480b964-a03c-45a2-975e-d78ab432900b.png)

## Vagrant

In this repo you well find a directory of the vagrant file.

### Setup the machines

Use the commands bellow:

```
cd vagrant/
vagrant up
```
after all the VMs created you can list the status of each one:

```
vagrant status

Current machine states:

haproxy-lb                running (virtualbox)
controller-0              running (virtualbox)
controller-1              running (virtualbox)
controller-2              running (virtualbox)
worker-0                  running (virtualbox)
worker-1                  running (virtualbox)
worker-2                  running (virtualbox)
```

### Machines ip address

| Machine Name  | IP Address      |
|---------------|-----------------|
| haproxy-lb    | 192.168.100.30  |
| controller-0  | 192.168.100.10  |
| controller-1  | 192.168.100.11  |
| controller-2  | 192.168.100.12  |
| worker-0      | 192.168.100.20  |
| worker-1      | 192.168.100.21  |
| worker-2      | 192.168.100.22  |


## Configure HAPROXY LB

ssh to the haproxy-lb VM
```
vagrant ssh haproxy-lb
```
After that configure the backend and frontend in the lb

```
nano /etc/haproxy/haproxy.cfg

##############################################
frontend k8s
  bind 192.168.100.30:80
  mode tcp
  default_backend k8s

backend k8s
  balance roundrobin
  mode tcp
  option tcplog
  option tcp-check
  server controller-0 192.168.100.10:80 check
  server controller-1 192.168.100.11:80 check
  server controller-2 192.168.100.12:80 check
##############################################

systemctl enable haproxy
systemctl start haproxy
```

Next: [Installing the Client Tools](02-client-tools.md)
