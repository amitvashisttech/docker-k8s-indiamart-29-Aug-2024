# Setting up NFS Server for K8s PV Demo. 

## Install Nfs Server om Master Node.
```
apt-get install nfs-kernel-server -y 
mkdir /exports
chown nobody:nogroup /exports
```

## NFS Export Path & Share Config
```
root@kube-master:# grep -i exports /etc/exports
/exports  *(rw,sync,no_subtree_check)
root@kube-master:#
```

## Restart the NFS Server Service
```
systemctl restart nfs-kernel-server
systemctl status  nfs-kernel-server
```

## Vertify the NFS Share
```
showmount -e localhost 
```


# On Clinet / Worker Nodes 

## Install NFS Clinet Utils 
```
apt-get install nfs-common -y
mount -t nfs 172.31.0.100:/exports /mnt/
hostname >> /mnt/hostname.txt ; umount /mnt
```
