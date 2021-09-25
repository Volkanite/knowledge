## MASTER & WORKER
`sudo su`  
`vim /etc/apt/sources.list.d/kubernetes.list`

    deb https://apt.kubernetes.io/ kubernetes-xenial main

`curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -`  
`apt-get update`  
`apt-get install docker.io`   
`apt-get install kubectl` [master only]  
`apt-get install kubeadm`  

`vim /etc/docker/daemon.json`

    { 
    "exec-opts": ["native.cgroupdriver=systemd"]
    }

`systemctl daemon-reload`  
`systemctl restart docker`  
`systemctl restart kubelet`


## MASTER  
`kubeadm init`  

`cp /etc/kubernetes/admin.conf $HOME/`  
`chown $(id -u):$(id -g) $HOME/admin.conf`  
`export KUBECONFIG=$HOME/admin.conf`  

`kubectl get nodes`


## WORKER
join_example:

    kubeadm join 172.31.19.161:6443 --token ookiaj.x295hsff709mfug1 --discovery-token-ca-cert-hash sha256:e3b592ca6221d731e8fb7aa21bba7c277b4b692d45484c021e352b2194c355ce
