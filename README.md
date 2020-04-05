# Download helm 

curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 <br/>
chmod 700 get_helm.sh <br/>
./get_helm.sh

# git clone the helm repo to setup tiller

git clone https://github.com/naveenramasamy11/helm.git

# create Service Account

kubectl create -f helm/serviceAccount.yaml

# DO NOT TRY IT IN PRODUCTION 
# For demo purpose we will create a role binding to cluster-admin.

kubectl create -f helm/role-binding.yml

# create Service account

# Initialize tiller
helm init --service-account tiller --wait
