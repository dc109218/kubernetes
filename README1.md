#//ubuntu
#nano ~/.bashrc

#//mac os
#nano ~/.zshrc

#//Window
#nano "C://Program Files/Git/etc/profile.d/aliases.sh"

#export PS1="#root#-> "

#alias mrole='k port-forward -n mrole svc/mongo-node-1 27020:27017'
#alias rrole='k port-forward -n mrole svc/proredis-master 6379:55622'

alias ps32='openssl rand -hex 16'
alias ps64='openssl rand -hex 32'
alias ps128='openssl rand -hex 64'

#export KUBECONFIG=~/role-kubeconfig.yaml

//alias mbkp='ssh -i ~/dcs_admin_main.pem ubuntu@65.0.164.135'

#alias eksapin='aws eks update-kubeconfig --name hum-apin --region ap-south-1'
#alias gksapin='gcloud container clusters get-credentials hum-com --zone asia-south1-b --project humcom'

#alias pf='k port-forward -n mongo svc/romongo-mongodb-headless 27017:27017'
#alias mongolocal='k port-forward -n mongo svc/romongo-mongodb-headless 27017:27017'
alias ktop='kubectl describe nodes'

alias sz='du -hc'

alias c='clear'
alias k='kubectl'
alias kdn='kubectl top nodes'
alias svc='kubectl get svc -A'
alias all='kubectl get all -A'
alias pods='kubectl get pods -A'
alias pv='kubectl get pv,pvc -A'
alias st='kubectl get storageclass -A'
alias dp='kubectl get deployment -A'
alias sf='kubectl get statefulset -A'
alias ns='kubectl get namespace'
alias ing='kubectl get ingress -A'
alias ddk='kubectl delete -f'
alias adk='kubectl apply -f'
alias rs='kubectl get rs -A'
alias ln='sudo lsof -i -P -n | grep LISTEN'
alias pg='pwgen 6 5'

alias gp='git pull origin -f'
alias gf='git fetch'
