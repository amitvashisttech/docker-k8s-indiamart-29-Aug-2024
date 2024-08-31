# Load Gen: 

# kubectl run -i --tty load-gen --image=busybox /bin/sh

$ wget http://hpa-example.default.svc.cluster.local:31001

$ while true; do wget -q -O- http://hpa-example.default.svc.cluster.local:31001; done

