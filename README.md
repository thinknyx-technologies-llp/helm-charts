Steps to install HELM 3 on Kubernetes Cluster

1. Install wget on your master
2. wget https://get.helm.sh/helm-v3.0.2-linux-amd64.tar.gz
3. untar -xvf helm-v3.0.2-linux-amd64.tar.gz
4. cp linux-amd64/helm /usr/bin/helm 
5. helm version 
6. helm ls # to list the current deployed releases
7. helm install release-name helm-package

   example:
   
   1. helm install kubernetes-dashboard https://kmayer10.github.io/helm-charts/mychart-0.1.0.tgz
   2. helm upgrade kubernetes-dashboard https://kmayer10.github.io/helm-charts/mychart-0.1.1.tgz
   3. helm history kubernetes-dashboard #to check the Release Revision
   4. helm rollback kubernetes-dashboard revision <release revision number to rollback to>
   
   5. helm create <chart name> # to create chart template to be prepared
      
   6. Sample Helm Chart Structure  --  https://github.com/kmayer10/helm-charts/tree/master/mychart
   
   7. helm package <chart folder location> # to create helm chart
   8. helm repo add <repo-name> <repo-link> # to add online repo as local repo to download existing helm charts, you can consider them as yum repos or docker-registries
   
   9. helm repo index <chart folder location> --url https://kmayer10.github.io/helm-charts to create index.yaml file which is used by above command to add online repo as HELM Local Repository
