# ckad-learning
  * I am preparing for CKAD exam. I will be adding the hand-on lab excercies I executed during the learning.  

# Apache HTTPD
  * Refer to yml files under _apache-https-deployment-service_ folder to deploy httpd  with container port on 80 and expose the httpd service for external access.
  
# Petclinic SpringBoot Application
  * Refer to yml files under _petclinic-deployment-service_ folder to deploy springboot application with container port on 8080 and expose the app for external access.
  
# Prometheus Metrics
  * Refer to yml files under _prometheus-deployment-service_ folder to deploy Prometheus with container port on 9090 and expose the /metrics for external access.
  
# Jenkins
  * Refer to yml files under _jenkins-deployment-service_ folder to deploy Jenkins with container port on 8080 and expose it for external access.
     - First time access to Jenkins requires  administrator password, follow below steps;
       - Logint to one of the pod using command _kubectl exec -it  jenkins-deploy-5f8969fd59-2qdgs  -- bash_
       - Navitage to Jenkins secrets folder _/var/jenkins_home/secrets/_
       - Copy contents of file _cat initialAdminPassword_
       - Provide the password in Jenkins home page

