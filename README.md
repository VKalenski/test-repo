# test-repo

test



wireshrak


mdns

nbns

eth.addr == aa:bb:cc:dd:ee:ff

mdns && frame contains "Kalenski"




OLD_PV=$(kubectl get pvc "$OLD" -n "${{ inputs.usage }}-${{ inputs.customer }}-$BUNDLE_VERSION" -o jsonpath='{.spec.volumeName}')

kubectl get pvc -n test-us-ppd-25-3-1 -o jsonpath="{.items[*].metadata.name}" | tr ' ' '\n'

kubectl get pvc test-us-ppd-25-3-1-docs -n test-us-ppd-25-3-1 -o jsonpath='{.spec.volumeName}'

kubectl get pv pvc-245f3b60-fe8d-4102-a939-c362691908e4 -o jsonpath='{.spec.csi.volumeHandle}' | cut -d'#' -f2

https://$STORAGE_ACCOUNT.file.core.windows.net/$OLD_SHARE?$SAS_TOKEN

az storage account show \
  --name f6187ceb2bd3c4fa49b787e \
  --resource-group MC_rg-ecad-ig-dev-shmplm-we_aks01-ig-dev-we4712_westeurope


---

### HELM

helm template .

  --- 

### Minikube

minikube version
choco upgrade minikube -y
minikube delete
minikube start

---

Start Administrator PowerShell & Go to the directory

---

**Check vagrant installation and version**
> vagrant --version

---

**Update vagrant version**
> choco upgrade vagrant

---

**Инициализиране на Vagrantfile**
> vagrant init
>
> vagrant init hashicorp/bionic64

---

**Creating VM in Hyper-V**
> vagrant up
>
> vagrant up --debug
>
> vagrant up --provider=hyperv
>
> vagrant up --provider=hyperv --debug

***Options:***
> ```--provider=hyperv```
>
> ```--provider=virtualbox```

---

**Връзка с машината чрез ssh през Terminal**
> vagrant ssh
>
> vagrant ssh --debug

---

**Delete the Virtual Machine**
> vagrant destroy
>
> vagrant destroy --debug

  ---

  ### KIND

  choco install kind

  ---

  Abreviatura

KaaS - Kubernetes-as-a-Service ( for example: Azure Kubernetes Service, Amazon EKS, Google GKE,  )
DNS - Domain Name System

---

### KIND

choco install kind

kind create cluster --name kalenski-cluster
