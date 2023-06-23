# k8s
Kubernetes related repository

**k8scp.sh**
Run the script as an argument to thebashshell. You will need thekubeadm joincommand shown near the end of theoutput when you add the worker/minion node in a future step. Use the tee command to save the output of the script, in case you cannot scroll back to find the kubeadm join in the script output.  Please note the following is one command and then its output.
Using Ubuntu 20.04 you may be asked questions during the installation. Allow restarts (yes) and use the local, installed software if asked during the update, usually (option 2).

Run master node installation with 
[root@hrzg1ku01 s_02]# bash k8scp.sh | tee $HOME/cp.out

**k8sWorker.sh**
Run worker node installation with
[root@hrzg1ku01 s_02]# bash k8sWorker.sh | tee worker.out

When the script is done the worker node is ready to join the cluster.  Thekubeadm join statement can be found near the end of the kubeadm init output on the master/control plane node. It should also be in the file cp.out as well. Example:
[root@hrzg1ku01 s_02]# kubeadm join --token 118c3e.83b49999dc5dc034 \10.128.0.3:6443 --discovery-token-ca-cert-hash \sha256:40aa946e3f53e38271bae24723866f56c86d77efb49aedeb8a70cc189bfe2e1d
