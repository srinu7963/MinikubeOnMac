# MinikubeOnMac


installing brew..


/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


brew install tree

brew install minikube

brew install docker


create docker A/c and login into dockerhub website, create Access id & generate key...

docker login 

eroor: 

---------------
You should delete the line with credsStore from ~/.docker/config.json or rename credsStore to credStore.

explanation:

The property credsStore specifies an external binary to serve as the default credential store. 
When this property is set, docker login will attempt to store credentials in the binary specified by docker-credential-<value> which is visible on $PATH. If this property is not set,
credentials will be stored in the auths property of the config.

For Arch Linux edit the ~/.docker/config.json file and paste this code

{
    "auths": {},
    "credStore": "desktop",
    "currentContext": "default"
}
basically change credsStore to credStore

---------------
now try docker login


minikube start
minikube start --driver=docker



helm repo add kubearmor https://kubearmor.github.io/charts

helm repo update kubearmor

helm upgrade --install kubearmor-operator kubearmor/kubearmor-operator -n kubearmor --create-namespace

kubectl apply -f https://raw.githubusercontent.com/kubearmor/KubeArmor/main/pkg/KubeArmorOperator/config/samples/sample-config.yml 

