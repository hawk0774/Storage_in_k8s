# Хранение в K8s
## Объяснение поведения ресурсов (2 задание):
После удаления Deployment и PVC, PV остается в статусе Released. Дело в том, что PV не удаляется автоматически, так как политика persistentVolumeReclaimPolicy: Retain указывает на сохранение данных. ​Файл сохраняется на ноде и данные в директории /tmp/k8s-data остаются на узле, так как hostPath привязан к файловой системе узла.
После удаления PV, файл остается на диске, потому что удаление PV в Kubernetes не удаляет физические данные на узле, так как PV - это абстракция над хранилищем, а не само хранилище.


![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_1.png)

![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_2.png)

![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_3.png)

![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_4.png)

![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_5.png)

## В Minikube на WSL2 путь /tmp/k8s-data/ находится внутри виртуальной машины Minikube,нужно подключиться к ноде Minikube.
![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_6.png)

![alt text](https://raw.githubusercontent.com/hawk0774/Storage_in_k8s/main/Screenshot_7.png)
