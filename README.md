# kubernetes-app

## Installing

### Install kubectl on Linux

<https://k8s-docs.netlify.app/en/docs/tasks/tools/install-kubectl/>

    ```shell
    curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

    chmod +x ./kubectl

    sudo mv ./kubectl /usr/local/bin/kubectl

    kubectl version --client
    ```

### Install Minikube

<https://k8s-docs.netlify.app/en/docs/tasks/tools/install-minikube/>

    ```shell
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
    && chmod +x minikube

    sudo mkdir -p /usr/local/bin/
    sudo install minikube /usr/local/bin/
    ```

### Personal note

Minikube:

- minikube status: watch status in minkube
- minikube start: start status in minkube
- minikube stop: stop status in minkube
- minikube service --url [name of the service]: get the url to this service

Kubectl:

- kubectl run [name of the app in kubernetes] --image=[name of the image:version] --port=[port_intranet_kubernet port_image]; create a pod with an docker image (kubectl run kbillingapp --image=sotobotero/udemy-devops:0.0.1 --port=80 80)

- kubectl get pods: view pods

- kubectl describe pod [name of the app in kubernetes]: show more information about the pod

- kubectl describe service [name of the service in kubernetes]: show more information about the service

- kubectl expose pod kbillingapp --type=LoadBalancer --port=[port to exporse to outside] --target-port=[intranet kubernetes port]: expose a pod as a services (kubectl expose pod kbillingapp --type=LoadBalancer --port=8080 --target-port=80)

- kubectl get services: watch services

- kubectl api-versions: watch versions

- kubectl apply -f [name/path]: create an specification from a file

- kubectl delete -f [name/path]: delete an specification from a file

Utils:

- echo -n [value] | base64: codify the value in base 64
- echo -n [value] | base64: codify the value in regular base
