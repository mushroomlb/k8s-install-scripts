# 1 rancher server单节点 

**rancher v1.6.11支持kubernetes 1.8版本**

master节点安装完成后，通过8080端口访问rancher管理界面。

master节点执行下面的命令，master节点除了安装docker环境，还安装rancher server：
```bash
sh setup.sh master
```

slave节点执行下面命令，slave节点只安装docker环境：
```bash
sh setup.sh slave
```

# 2 rancher server单节点外部数据库部署

master节点执行下面的命令，master节点除了安装docker环境，还安装mariadb和rancher server：
```bash
sh setup.sh master 192.168.0.1
```
> 注意：192.168.0.1为master节点IP

slave节点执行下面命令，slave节点只安装docker环境：
```bash
sh setup.sh slave
```

# 3 rancher上部署kubernetes

master节点安装完成后，参考【原生加速中国区Kubernetes安装】https://www.cnrancher.com/kubernetes-installation/ 安装kubernetes。


从rancher页面生成kubeconfig配置文件，保存到master节点~/.kube/config文件中，下载kubectl文件到master节点/usr/bin目录，设置文件为可执行文件 chmoc a+x /usr/bin/kubectl。kubectl已经上传到百度网盘 https://pan.baidu.com/s/1jH9dsF0 

参考：

【原生加速中国区Kubernetes安装】https://www.cnrancher.com/kubernetes-installation/

【Installing Rancher Server】http://rancher.com/docs/rancher/latest/en/installing-rancher/installing-server/#multi-nodes

# 4 安装重置
先在rancher界面删除所有节点，再在每个节点执行reset.sh脚步。
