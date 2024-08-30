# K8s Datastore - ETCD

## Check the status of ETCD
```
kubectl get pods -n kube-system | grep -i  etcd
```

## Let explore ETCD POD
```
kubectl exec -it etcd-master -n kube-system   -- /bin/sh
```

## Export the below Env for Smooth ETCD Interations:
```
export ETCDCTL_API=3
export ETCDCTL_CACERT=/etc/kubernetes/pki/etcd/ca.crt
export ETCDCTL_CERT=/etc/kubernetes/pki/etcd/server.crt
export ETCDCTL_KEY=/etc/kubernetes/pki/etcd/server.key
```



## Check the ETCD Status
```  
etcdctl endpoint status  --write-out=table
```

```
+----------------+------------------+---------+---------+-----------+------------+-----------+------------+--------------------+--------+
|    ENDPOINT    |        ID        | VERSION | DB SIZE | IS LEADER | IS LEARNER | RAFT TERM | RAFT INDEX | RAFT APPLIED INDEX | ERRORS |
+----------------+------------------+---------+---------+-----------+------------+-----------+------------+--------------------+--------+
| 127.0.0.1:2379 | c22785f83a00f446 |   3.4.3 |  5.0 MB |      true |      false |         2 |      37052 |              37052 |        |
+----------------+------------------+---------+---------+-----------+------------+-----------+------------+--------------------+--------+

```

## Checking the ETCD Prefix
```
etcdctl  get / --prefix --keys-only
```

## ETCD Backup
```
etcdctl  --endpoints=https://127.0.0.1:2379 snapshot save /tmp/backup.db
```

## ETCD Snapshot
```
etcdctl snapshot status /tmp/backup.db
```


## Sample Scripts 

### Automating the backup

#### You can automate the backup process using a cron job. Create a script etcd-backup.sh:

```

#!/bin/bash

# Environment variables
export ETCDCTL_API=3
export ETCDCTL_CACERT=/etc/kubernetes/pki/etcd/ca.crt
export ETCDCTL_CERT=/etc/kubernetes/pki/etcd/server.crt
export ETCDCTL_KEY=/etc/kubernetes/pki/etcd/server.key

# Backup file path
BACKUP_FILE="/path/to/backup-$(date +%Y%m%d%H%M%S).db"

# Take the backup
etcdctl --endpoints=https://127.0.0.1:2379 snapshot save $BACKUP_FILE

# Verify the backup
etcdctl snapshot status $BACKUP_FILE
```

#### Make the script executable:
```
chmod +x etcd-backup.sh
```

#### Add a cron job to automate the backup (e.g., daily at midnight):
```
crontab -e
```

#### Add the following line:
```
0 0 * * * /path/to/etcd-backup.sh >> /var/log/etcd-backup.log 2>&1
```
