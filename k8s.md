# sudo nano /etc/hostname
sudo apt-get update -y && sudo apt-get upgrade -y

sudo snap list
sudo snap info microk8s
sudo snap install microk8s --classic

microk8s status

microk8s start
microk8s stop

sudo usermod -a -G microk8s $USER
sudo chown -f -R $USER ~/.kube
su - $USER

microk8s kubectl get all --all-namespaces

# service addon add
microk8s enable --help
microk8s disable <name>
microk8s enable metrics-server helm3
microk8s enable dns hostpath-storage
microk8s config

# alias
echo "alias kubectl='microk8s kubectl'" >> ~/.bashrc
echo "alias k='kubectl'" >> ~/.bashrc
echo "alias c='clear'" >> ~/.bashrc
microk8s config > ~/.kube/config

# node add
microk8s add-node
microk8s join 10.0.49.188:25000/6c05e9e0029a24c21ce46b922781ebca/8a6521a58671
microk8s leave
microk8s remove-node 10.0.66.74

# remove node
# remove node in command run
microk8s leave
# main node run command

===
/var/snap/microk8s/common/default-storage/dredis-redis-data-devredis-master-0-pvc-4e23dd1f-3d27-4055-b46e-3abddc372410
/var/snap/microk8s/common/default-storage/dredis-redis-data-devredis1-master-0-pvc-4b3b2688-9bb1-40e0-9404-0d90914d72a5