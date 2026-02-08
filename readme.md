# Cluster preparation

- create namespace `prod` and `stage`
- add gp3 ebs and efs storage class to cluster
- create backend-pvc for prod and stage
- create secret, configmap for prod, stage
- for the first time add init container for mongodb-ss
- create prod, stage argo cd applications

## edge cases

- when we delete the prod folder from `k apply -k ./prod` it deleted the backend pvc and backend deployment. When create we create pro folder again, it will create another pvc and another efs pv. to avoid that we can create pvc from a separate folder
