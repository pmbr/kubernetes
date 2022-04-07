# kubernetes

### kubernetes knowledge base

kubectl create -f <yaml file>

kubectl delete pod <pod name>


kubectl edit pod <pod>

kubectl create configmap <config-name> --from-literal=<key>=<value>


kubectl create configmap config-map-test --from-literal=cor=azul

kubectl create configmap <config-name> --from-file=<path-to-file>


kubectl create configmap config-map-test-2 --from-file=config-map-file.map


Para ver node do pod:

    kubectl get pods -o wide


Para rodar um pod sem yaml:

    kubectl run <name> --image=<image>

kubectl run <name> --image=<image> --dry-run=client -o yaml > arquivo.yml

kubectl describe pod <pod> | grep -i image    

kubectl scale --replicas=<n> replicset <name>

kubectl create deployment  --dry-run=client --image=httpd:2.4-alpine httpd-fronted -o yaml > depl.yml


kubectl config set-context $(kubectl config current-context) --namespace=<namespace>



kubectl run --image=<image> --labels=k=v

kubectl create deployment --image=<image>

kubectl expose deployment <name> --port <port>

kubectl scale replicaset/deployment <name> --replicas=<replicas>

kubectl set image pod/deployment/replicaset <name> <old>=<new>

kubectl expose pod redis --name=redis-service --port=6379

kubectl run custom-nginx --image=nginx --port=8080 --expose

kubectl get pods --selector <key>=<value> 

kubectl get pods -l <key>=<value> 

kubectl get pods --show-labels

kubectl get pods --selector <key>=<value>,<key>=<value>

--no-headers | wc -l


kubectl taint nodes node-name key-value:effect

kubectl taint nodes node-name key-value-

kubectl explain pod --recursive | less

kubectl label nodes <node-name> <k>=<v>