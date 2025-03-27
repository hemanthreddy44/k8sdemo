install  local path provisioner

kubectl apply -f https://raw.githubusercontent.com/rancher/local-path-provisioner/v0.0.31/deploy/local-path-storage.yaml

kubectl get sc


diplay output

NAME         PROVISIONER             RECLAIMPOLICY   VOLUMEBINDINGMODE      ALLOWVOLUMEEXPANSION   AGE
local-path   rancher.io/local-path   Delete          WaitForFirstConsumer   false                  7m24s


k get pvc
k get pv


kubectl create -f https://raw.githubusercontent.com/rancher/local-path-provisioner/master/examples/pvc/pvc.yaml
kubectl create -f https://raw.githubusercontent.com/hemanthreddy44/k8sdemo/refs/heads/main/storage/pod.yaml


kubectl get pod

kubectl exec volume-test -- sh -c "echo local-path-test > /data/test"

delete the pod


create pod again 
kubectl create -f https://raw.githubusercontent.com/hemanthreddy44/k8sdemo/refs/heads/main/storage/pod.yaml

 kubectl exec volume-test -- sh -c "cat /data/test"

