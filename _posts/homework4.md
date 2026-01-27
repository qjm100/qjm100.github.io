---
title: homework4
date: 2025-05-18 21:33:16
tags: homework
---

# homework4保姆级教程

**重要提醒：请装好minikube环境**

**ps，minikube安装方法**

开启魔法上网，打开ubuntu
```shell
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
minikube start
```

### 1.下载文件

--------------------

修改文件名中的xxx为自己全名，并且文件内也有xxx也要修改为全名

### 2.启动docker和ubuntu
右击文件所在目录空白位置

点击在此处打开终端

***一行一行输入指令***

```shell
wsl
cp xxx-nginx-deployment.yaml ~ #xxx改成你的全名
cp xxx-node-service.yaml ~ #xxx改成你的全名
cd ~
kubectl apply -f xxx-nginx-deployment.yaml #xxx改成你的全名
kubectl apply -f xxx-nodeport-service.yaml #xxx改成你的全名
kubectl get deployment xxx-nginx-deployment #xxx改成你的全名
kubectl get service xxx-nodeport-service #xxx改成你的全名
minikube service xxx-nodeport-service #xxx改成你的全名
```

此时安装完成，使用浏览器打开终端上面的链接，按要求进行截图即可