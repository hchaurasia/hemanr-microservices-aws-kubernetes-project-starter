# DESCRIPTION
This Coworking Space Service Extension project deploys a analytics code to demo the deployment process in AWS using Kubernetes and display skills in using CI/CD principles and configurations for monitoring the cluster using CloudWatch.

# PROJECT COMPONENTS 
    1. Analytics application exposing two APIs
    2. PostgreSQL DB used by Analytics application to server the API requests.

# PROJECT ARCHITECTURE
    1. This project makes use of an AWS EKS cluster to deploy the Analytics application and a PostgreSQL database. 
    2. The Docker image used for the deployment is stored in an ECS repository.
    3. Docker image is build using a AWS Codebuild pipeline.
    4. The Code for the Analytics application and Database is kept in a Github repository.
    5. The codebuild pipeline is triggered usingh a webhook on repository PUSH operation into main baranch.
    6. The container logs can be monitored in CloudWatch container insight.

# PROJECT INFRA DETAILS
    1. AWS EKS Cluster : my-cluster
    2. Cluster Node Group : ms-node-grp
    3. ECR Repository : coworkingrepo
    4. AWS Codebuild Project : coworkingcodebuild
    

# Process to deploy a new application version.
    1. Ensure the Codebuild pipeline is triggered against the latest version and a new docker image is available in ECR registry.
    2. Download the updated version of the github repository.
    3. Open the file deployment/coworking.yaml
    4. Update the new docker image url. You may copy the url from ECR registry in the AWS console.
    5. Apply the changes using "kubectl apply -f coworking.yaml" command.
    6. You may verify the status using kubectl get pods/svc commands.
    7. Test your application by running the APIs using curl commands.
# Deliverables
    1.Dockerfile 
    2.Screenshot of AWS CodeBuild pipeline (CloudWatch_Logs.png)
    3.Screenshot of AWS ECR repository for the application's repository(ECR.png)
    4. Screenshot of kubectl get svc
    5. Screenshot of kubectl get pods (Ruunin_pods.png)
    6. Screenshot of kubectl describe svc <DATABASE_SERVICE_NAME> (Desc_DBService.png)
    7. Screenshot of kubectl describe deployment <SERVICE_NAME> (Desc_CoworkingService.png)
    8. All Kubernetes config files used for deployment (ie YAML files)
    9. Screenshot of AWS CloudWatch logs for the application((CloudWatch_Logs.png))
    10. curl a7895d18f655948faadcea43c8c484de-1808627719.us-east-1.elb.amazonaws.com:5153/api/reports/daily_usage
    11. Github Repository : https://github.com/hchaurasia/hemanr-microservices-aws-kubernetes-project-starter
    12. README.md 
