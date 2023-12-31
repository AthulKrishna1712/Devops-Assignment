# Devops-Assignment
---
Deploying a web application using Kubernetes
---

**1) Set up a Java web application named "Book Store" as base project**

**2) Created the database for using MySql**

* Created an EC2 instance for database
* Installed MySql on the instance
* Set a user and given the privilages
* Created a database named "bookdb"

**3) Created a backup for the MySql database in AWS**
    
 * using EBS Volume
 * Also created a cronjob for make it work on every day in a year

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2020-16-50.png" height=300 width=600>

**4) Build and packaged it using Maven**
    
 * Also checked it locally and it runs perfectly

**5) Containerized the web application using Docker**

 * Created a Dockerfile to generate a Docker image from the application
 * Dockerfile is uploaded

**6) Pushed the image to the DockerHub**
    
 * URL:- https://hub.docker.com/r/athulkrishna1712/bookstore/tags

  <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2014-03-50.png" height=600 width=1200>
    
**7) Created 3 EC2 instances for making Kubernetes Cluster**
  * One for Master node and two for Worker nodes

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2014-04-20.png" height=600 width=1200>

**8) Created a cluster using these 3 instances by Kubeadm**

**9) Created a Deployment(webapp.yaml) file and service file(service.yaml) for creating the pods a service**
  * The image pushed earlier to dockerhub is given in the deployment file and service is given using NodePort

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-14%2000-22-39.png" height=600 width=1200>

**10) Deployed the Web application using Kubernetes**
    (can be accessed with worker node ip and nodeport)

 <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2013-07-21.png" height=600 width=1200>

 <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2013-09-20.png" height=600 width=1200>

 <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2013-09-48.png" height=600 width=1200>

 <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2013-50-24.png" height=600 width=1200>


**11) Created an Application Load Balancer in AWS containing the target group with 2 worker nodes**
 * But there were some issues with accessing the webapp, when it is done with Kubeadm
 * One worker was unhealthy sometimes and we couldn't access the webapp
 * But problem is solved by using the "Amazon EKS"
 * Now nodes are running perfectly and the webapp is accessble.

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-14%2014-49-46.png" height=600 width=1200>
    
**Loaded using Load Balancer URL:**
 <img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2017-44-14.png" height=600 width=1200>

---
Jenkins Pipeline:
---
* Automation was introduced by a Jenkins pipeline using a Scripted pipeline script
* Cloned the repository from github
* Used Maven for building and packaging
* Pushed the code to SonarQube for code scan
* Pushed the file to Nexus Repository
* Build the Image and pushed it to DockerHub
* Deploy the webapp using Kubernetes

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-15%2014-48-34.png" height=600 width=1200>


**Open Blue Ocean:**

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2020-49-40.png" height=600 width=1200>

**Nexus Repository:**

<img src="https://github.com/AthulKrishna1712/Devops-Assignment/blob/main/Screenshots/Screenshot%20from%202023-09-13%2020-48-21.png" height=600 width=1200>
