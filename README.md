# k8s
Kubernetes related repository

k8scp.sh
Run the script as an argument to thebashshell. You will need thekubeadm joincommand shown near the end of theoutput when you add the worker/minion node in a future step. Use the tee command to save the output of the script, in case you cannot scroll back to find the kubeadm join in the script output.  Please note the following is one command and then its output.
Using Ubuntu 20.04 you may be asked questions during the installation. Allow restarts (yes) and use the local, installed software if asked during the update, usually (option 2).

Finally, run master node installation with 
[root@hrzg1ku01 s_02]# bash k8scp.sh | tee $HOME/cp.out
