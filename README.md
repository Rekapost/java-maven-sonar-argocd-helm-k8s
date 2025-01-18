# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)


Here are the step-by-step details to set up an end-to-end Jenkins pipeline for a Java application using SonarQube, Argo CD, Helm, and Kubernetes:

Prerequisites:

   -  Java application code hosted on a Git repository
   -  Jenkins server
   -  Kubernetes cluster
   -  Helm package manager
   -  Argo CD

Steps:

    1. Install the necessary Jenkins plugins:
       1.1 Git plugin
       1.2 Maven Integration plugin
       1.3 Pipeline plugin
       1.4 Kubernetes Continuous Deploy plugin

    2. Create a new Jenkins pipeline:
       2.1 In Jenkins, create a new pipeline job and configure it with the Git repository URL for the          Java application.
       2.2 Add a Jenkinsfile to the Git repository to define the pipeline stages.

    3. Define the pipeline stages:
        Stage 1: Checkout the source code from Git.
        Stage 2: Build the Java application using Maven.
        $  mvn clean package
        $ java -jar target/spring-boot-web.jar
        $ java -jar target/spring-boot-web.jar --server.port=8081
        $ docker build -t ultimate-cicd-pipeline:v1 .
        $ docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1
        ![image](https://github.com/user-attachments/assets/ddf898c1-044f-4dfc-951a-82e0ba60a230)
        Stage 3: Run unit tests using JUnit and Mockito.
        Stage 4: Run SonarQube analysis to check the code quality.
       ![image](https://github.com/user-attachments/assets/772acb93-9245-4c06-a910-c4601aa81646)

        Stage 5: Package the application into a JAR file.
        $ mvn clean package
        $ ls target
         classes/            maven-archiver/  spring-boot-web.jar
         generated-sources/  maven-status/    spring-boot-web.jar.original  

        Stage 6: Deploy the application to a test environment using Helm.
        Stage 7: Run user acceptance tests on the deployed application.
        Stage 8: Promote the application to a production environment using Argo CD.

    4. Configure Jenkins pipeline stages:
        Stage 1: Use the Git plugin to check out the source code from the Git repository.
        Stage 2: Use the Maven Integration plugin to build the Java application.
        Stage 3: Use the JUnit and Mockito plugins to run unit tests.
        Stage 4: Use the SonarQube plugin to analyze the code quality of the Java application.
        ![image](https://github.com/user-attachments/assets/3d2c7e22-4512-4997-a7d9-ec4f2b10e30d)

        Stage 5: Use the Maven Integration plugin to package the application into a JAR file.
        Stage 6: Use the Kubernetes Continuous Deploy plugin to deploy the application to a test environment using Helm.
        Stage 7: Use a testing framework like Selenium to run user acceptance tests on the deployed application.
        Stage 8: Use Argo CD to promote the application to a production environment.
![image](https://github.com/user-attachments/assets/883c06f0-03a1-487e-82d7-c9b2e310c096)
![image](https://github.com/user-attachments/assets/760392d7-e3d5-4c9a-b995-21721d9f8814)
![image](https://github.com/user-attachments/assets/8bf96167-39ff-4706-a43f-3f069eb2bb9a)


    5. Set up Argo CD:
        Install Argo CD on the Kubernetes cluster.
        Set up a Git repository for Argo CD to track the changes in the Helm charts and Kubernetes manifests.
        Create a Helm chart for the Java application that includes the Kubernetes manifests and Helm values.
        Add the Helm chart to the Git repository that Argo CD is tracking.

    6. Configure Jenkins pipeline to integrate with Argo CD:
       6.1 Add the Argo CD API token to Jenkins credentials.
       6.2 Update the Jenkins pipeline to include the Argo CD deployment stage.

    7. Run the Jenkins pipeline:
       7.1 Trigger the Jenkins pipeline to start the CI/CD process for the Java application.
       7.2 Monitor the pipeline stages and fix any issues that arise.

This end-to-end Jenkins pipeline will automate the entire CI/CD process for a Java application, from code checkout to production deployment, using popular tools like SonarQube, Argo CD, Helm, and Kubernetes.


