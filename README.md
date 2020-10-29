k8s.gcr.io/kube-apiserver:v1.19.3
k8s.gcr.io/kube-controller-manager:v1.19.3
k8s.gcr.io/kube-scheduler:v1.19.3
k8s.gcr.io/kube-proxy:v1.19.3
k8s.gcr.io/pause:3.2
k8s.gcr.io/etcd:3.4.13-0
k8s.gcr.io/coredns:1.7.0

cat README.md | grep k8s.gcr.io | grep -v grep |awk -F '/|:' '{print "echo \"FROM "$0"\" > Dockerfile."$2}' |sh
