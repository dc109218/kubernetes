microk8s enable hostpath-storage

scp -i ~/.ssh/role-prod-imac -r $PWD/deploy/ root@14.190.8.61:/rit/k8s/deploy
scp -i ~/.ssh/role-prod-imac -r $PWD/engine/ root@14.190.8.61:/rit/k8s/engine


# create docker ts
kubectl create secret docker-registry docker-sec -n dev \
  --docker-server=registry.facebook.com:5443 \
  --docker-username=xyz \
  --docker-password=7a3-b7bf-2fc6b69fd858 \
  --docker-email=xyz@gmail


# microk8s certificate issues resolved
sudo cp facebook_com.crt /usr/local/share/ca-certificates/
sudo update-ca-certificates
<!-- sudo microk8s stop;sudo microk8s start -->


/etc/letsencrypt/live/graph.atway.in/fullchain.pem
/etc/letsencrypt/live/graph.atway.in/privkey.pem
cp /etc/letsencrypt/live/graph.atway.in/fullchain.pem /rit/k8s/cert/atway.in.pem
cp /etc/letsencrypt/live/graph.atway.in/privkey.pem /rit/k8s/cert/atway.in.key.pem


kubectl rollout restart -n dev deploy/atwaygql-deploy
kubectl rollout restart -n engine deploy/hum-engine-deploy

k logs -n dev deploy/atwaygql-deploy -f
k logs -n engine deploy/hum-engine-deploy -f


http://atwaygql-svc.dev.svc.cluster.local/
http://atwaygql-svc.dev.svc.cluster.local/v4/gql

curl -fsS http://localhost:4000/v4/health

curl -fsS http://atwaygql-svc.dev.svc.cluster.local/v5/health



curl -fsS http://play-parity-svc.bot.svc.cluster.local