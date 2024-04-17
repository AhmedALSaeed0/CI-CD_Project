# CI/CD DevOps Project for Board Game

This project sets up a Continuous Integration and Continuous Deployment (CI/CD) pipeline for testing a board game. The pipeline includes setting up infrastructure on AWS, configuring EC2 instances, installing necessary tools such as Docker, SonarQube, Nexus, and Jenkins, and deploying the application using Kubernetes.

## Infrastructure Setup

- **VPC and Security Groups**: A Virtual Private Cloud (VPC) has been created on AWS, along with security groups to control inbound and outbound traffic. The necessary ports for the project have been opened in these security groups.

- **EC2 Instances**: Six EC2 instances have been provisioned on AWS:
  - `master`
  - `first-slave1`
  - `second-slave2`
  - `SonarQube`
  - `Nexus`
  - `Jenkins`

## Software Installation

- **Docker**: Docker has been installed on the master and slave nodes to containerize the application components and facilitate easy deployment.

- **Kubernetes (k8s)**:
  - `kubeadm` has been installed on the master node to set up a Kubernetes cluster.
  - `kubelet` has been installed on all nodes to manage Kubernetes pods.
  - `kubectl` has been installed as a command-line interface to interact with the Kubernetes cluster.

- **SonarQube**: SonarQube server has been set up using Docker:
  ```bash
  docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
  ```

- **Sonatype Nexus**: Nexus server has been set up using Docker:
  ```bash
  docker run -d --name nexus -p 8081:8081 sonatype/nexus3:latest
  ```

- **Jenkins**: Jenkins server will be installed on the Jenkins instance. The installation process will include setting up pipelines, configuring jobs, and integrating with other tools as needed.

## Next Steps

1. **Jenkins Setup**: Install Jenkins on the Jenkins instance and configure necessary plugins and jobs for the CI/CD pipeline.
2. **Pipeline Configuration**: Define Jenkins pipelines to automate the build, test, and deployment processes.
3. **Integration with SonarQube and Nexus**: Integrate Jenkins with SonarQube for code quality analysis and Nexus for artifact management.
4. **Deployment with Kubernetes**: Deploy the application using Kubernetes, managing containers and scaling as needed.
