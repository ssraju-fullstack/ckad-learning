# ckad-learning
  * I am preparing for CKAD exam. I will be adding the hand-on lab excercies I executed during the learning.  

# Apache HTTPD
  * Refer to yml files under _apache-https-deployment-service_ folder to deploy httpd  with container port on 80 and expose the httpd service for external access.
  
# Petclinic SpringBoot Application
  * Refer to yml files under _petclinic-deployment-service_ folder to deploy springboot application with container port on 8080 and expose the app for external access.
  
# Prometheus Metrics
  * Refer to yml files under _prometheus-deployment-service_ folder to deploy Prometheus with container port on 9090 and expose the /metrics for external access.
  
# Grafana Dashboard
  * Refer to yml files under _grafana-deployment-service_ folder to deploy Grafana with container port on 3000 and expose the dashboard for external access.
  
# Jenkins
  * Refer to yml files under _jenkins-deployment-service_ folder to deploy Jenkins with container port on 8080 and expose it for external access.
     - First time access to Jenkins requires  administrator password, follow below steps;
       - Logint to one of the pod using command _kubectl exec -it  jenkins-deploy-5f8969fd59-2qdgs  -- bash_
       - Navitage to Jenkins secrets folder _/var/jenkins_home/secrets/_
       - Copy contents of file _cat initialAdminPassword_
       - Provide the password in Jenkins home page
       
       
# Imperative Commands
   - Create a deployment named webapp using the image kodekloud/webapp-color with 3 replicas 
        * kubectl create deployment webapp --image=kodekloud/webapp-color --replicas=3 --dry-run=client -o yaml > webapp-definition.yaml
         
   -  Expose redis pod on ClusterIP 6379   
        * kubectl expose pod redis --port=6379 --name=redis-service --dry-run=client -o yaml > redis-service.yaml
        
   - Deploy Redis pod with image redis:alpine and label tier=db
        * kubectl  run redis --image=redis:alpine -l tier=db --dry-run=client -o yaml  > redis-definition.yaml  
       
   -  Create a new namespace called dev-ns
        * kubectl create namespace dev-ns --dry-run=client -o yaml > dev-ns-definition.yaml
    
   - Create a new deployment called redis-deploy in the dev-ns namespace with the redis image. It should have 2 replicas.
        * kubectl create deployment redis-deploy -n dev-ns --image=redis --replicas=2 --dry-run=client -o yaml > redis-deploy-definition.yaml
        
   - Create a pod called httpd using the image httpd:alpine in the default namespace
        * kubectl run httpd --image=httpd:alpine
        
   -  Create a service of type ClusterIP by the same name (httpd). The target port for the service should be 80. 
        * kubectl expose pod httpd --port=80

