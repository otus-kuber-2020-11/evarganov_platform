# evarganov_platform
evarganov Platform repository

## Задание 1
Все поды кроме coredns это static pod-ы управляемые напрямую kubelet-ом. 
Манифесты хранятся тут: 
```sh
# ls -l  /etc/kubernetes/manifests
total 20
-rw-r----- 1 root root 1532 Jan  1  0001 addon-manager.yaml.tmpl
-rw------- 1 root root 1812 Dec 15 11:11 etcd.yaml
-rw------- 1 root root 2889 Dec 15 11:11 kube-apiserver.yaml
-rw------- 1 root root 2492 Dec 15 11:11 kube-controller-manager.yaml
-rw------- 1 root root 1120 Dec 15 11:11 kube-scheduler.yaml
```
coredns описан в деплойменте `coredns`: 
```sh
...
Replicas:               1 desired | 1 updated | 1 total | 1 available | 0 unavailable
...
```
Под восстанавливает реплика сет. 
```sh
coredns-f9fd979d6   1         1         1       14h
```

## Задание 2
За основу был взят образ nginx:mainline-alpine.
Образ: [evarganov/otus-k8s-2020](https://hub.docker.com/repository/docker/evarganov/otus-k8s-2020)

## Задание 3
Под frontend не запускается из-за недостающих переменных окружения, которые были добавлены в манифест frontend-pod-healthy.yml