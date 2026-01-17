# FINAL TASK
## 1. Provisioning
### create server aws with terraform

> <img width="1867" height="62" alt="image" src="https://github.com/user-attachments/assets/41dfeafc-eebc-4cf0-921c-2fb00262cab6" />
> Here, I am using a service provider from AWS and Terraform to create a server using IaC. Here, I am only creating main. tf file for the server creation center and security_group.tf to open ports.

> <img width="1883" height="639" alt="image" src="https://github.com/user-attachments/assets/e21d332b-7e2d-44b9-be45-f81394d482a8" />
> In the program above, I use the Sydney region, specify the AMI (operating system used according to the region), specify the instance used (t3.small), specify the SSH key used, add a name tag for convenience, then call the security group that has been created, and add an output after finishing creating the VPS so that I don't need to return to the AWS console.

> <img width="1884" height="724" alt="image" src="https://github.com/user-attachments/assets/21efbcde-a6a0-4db9-9a88-a2a230c8fa87" />
> add the port configuration to be used, which means that if I add a new port later, “ # (1 unchanged attribute hidden)” will appear.

> <img width="1884" height="491" alt="image" src="https://github.com/user-attachments/assets/2c695791-a83d-4141-80a8-36b2e99d7c66" />
> Here, I use four servers. For the app server and gateway, I use BiznetGio, and for monitoring and app server 2, I use AWS. everything will be run with a new user, namely devops.

> <img width="1885" height="487" alt="image" src="https://github.com/user-attachments/assets/6e8ebfed-ee12-4445-b62f-1c947552ad14" />
> The ansible.cfg file serves as Ansible's main configuration file, which governs Ansible's default behavior when running playbooks, including SSH connections, authentication, and privilege escalation (sudo).

## 2. Repository

> <img width="1887" height="960" alt="image" src="https://github.com/user-attachments/assets/974b3d0d-82af-4946-8e56-dbade12d4540" />
> <img width="1884" height="864" alt="image" src="https://github.com/user-attachments/assets/02f6b06c-e8f6-4f53-a511-406cbb37a1bf" />
> <img width="1871" height="268" alt="image" src="https://github.com/user-attachments/assets/bc8114eb-4534-47bd-bcd8-40a270b452b5" />
> This playbook is used to set up the initial Git configuration on the application server. Its functions include creating an SSH directory, adding GitHub to known_hosts, setting up Git identity (username & email), cloning the frontend and backend template repositories, changing the remote to a private repository, and creating and pushing staging and production branches to GitHub.

> <img width="1881" height="966" alt="image" src="https://github.com/user-attachments/assets/447a43f9-7d96-4c63-9f49-d1a281a88ea2" />
> <img width="1882" height="630" alt="image" src="https://github.com/user-attachments/assets/cd0bf2a8-9ca8-4c7b-ab66-486f9f51dd70" />
> This playbook is used to update application code by pulling the frontend and backend repositories from GitHub based on a specific branch (default: staging). It is used on deployment servers to ensure that the running code always follows the latest version of the repository.

> <img width="1885" height="952" alt="image" src="https://github.com/user-attachments/assets/cb7097b0-f2be-4d22-bef4-e987c4310e2c" />
> <img width="1877" height="645" alt="image" src="https://github.com/user-attachments/assets/fdbc7ade-ccac-4f7e-9028-489353c32836" />
> This playbook is used to push local code changes to the GitHub repository. The script will automatically commit and then push to the staging and production branches for the frontend and backend, thereby simplifying the code synchronization process between environments.

## 3. setup configuration

> <img width="1884" height="976" alt="image" src="https://github.com/user-attachments/assets/2db99869-9c3f-43fc-a7fd-800df3dc9525" />
> <img width="1889" height="891" alt="image" src="https://github.com/user-attachments/assets/0d7555e9-e2e9-4da3-8789-101af77ac49d" />
> This playbook is used to install and set up Docker Engine on all hosts. The process includes updating the system repository, installing supporting dependencies, adding the GPG key and official Docker repository, installing Docker Engine and its components, ensuring that the Docker service runs automatically, and adding users to the docker group so that they can run Docker without root access.

> <img width="1884" height="970" alt="image" src="https://github.com/user-attachments/assets/290beb1f-3fee-42b7-ab17-7f56ac59550b" />
> <img width="1885" height="89" alt="image" src="https://github.com/user-attachments/assets/3d7fbc13-edfb-404b-874d-8bbe54d72e09" />
> This playbook is used to run Jenkins using Docker on a monitoring server. The process includes creating a Jenkins data storage directory, running the Jenkins container with the necessary ports and volumes, waiting until the initial password file is available, and displaying the Jenkins access URL and initial admin password for the initial setup process.

> <img width="1880" height="967" alt="image" src="https://github.com/user-attachments/assets/3e7122c2-72f2-4f64-bb90-3d7cd89fa2a2" />
> <img width="1892" height="806" alt="image" src="https://github.com/user-attachments/assets/e8d57963-fe41-4938-a3a1-15072fec322a" />
> <img width="1886" height="901" alt="image" src="https://github.com/user-attachments/assets/8b4b696f-fc80-4ad2-b5d6-065728ade457" />
> <img width="1894" height="387" alt="image" src="https://github.com/user-attachments/assets/9d814425-30d6-4d62-90b8-d4261fc1d034" />
> This playbook is used to deploy SonarQube along with a PostgreSQL database using Docker. The process includes creating directories and setting permissions for SonarQube data, adjusting the vm.max_map_count kernel parameter for Elasticsearch, running the PostgreSQL container as a database, and running the SonarQube container connected via a dedicated Docker network.

## 3. CI/CD

> <img width="1636" height="312" alt="image" src="https://github.com/user-attachments/assets/7f0763b8-36e4-47a1-9741-cb84195685ce" />
> adding credentials to log in to the server, git repository, and connecting to SonarQube

> <img width="1296" height="741" alt="image" src="https://github.com/user-attachments/assets/0d012001-31db-4e87-89f4-5ab54d20c6f7" />
> Using a Jenkins multibranch pipeline and performing Branch Sources to Git with an SSH repository and SSH Git credentials, then scanning all branches.

> <img width="1514" height="178" alt="image" src="https://github.com/user-attachments/assets/f9b72263-b98c-4b3b-b61a-01bfdbe27a28" />
> Then branches will appear as above in the form of staging and production according to the git repository.

> <img width="1194" height="533" alt="image" src="https://github.com/user-attachments/assets/85a5098f-f323-456f-b10d-a978d3f9773d" />
> Webhooks are used to trigger actions every time a push is made to a git repository by adding the Jenkins URL to the repository webhook.

> <img width="1463" height="115" alt="image" src="https://github.com/user-attachments/assets/7758b923-7e6a-4195-88f8-c3769b19e431" />
> To connect Jenkins with SonarQube, you need a token from SonarQube that has been entered into the Jenkins credentials.

> <img width="1660" height="786" alt="image" src="https://github.com/user-attachments/assets/c13ec0da-74ef-4805-8400-d08d0a821da5" />
> adding the SonarQube URL to the Jenkins system

> <img width="1612" height="635" alt="image" src="https://github.com/user-attachments/assets/642ecdd1-77d8-4bad-93a9-02bd6b2b0371" />
> adding SonarQube and Maven tools in Jenkins 

> <img width="1436" height="497" alt="image" src="https://github.com/user-attachments/assets/4a867edf-f5e3-4fc0-a498-13e1b0b6d46c" />
> After running Jenkins, the project will automatically appear in SonarQube.

## 4. Deploy

> <img width="1886" height="520" alt="image" src="https://github.com/user-attachments/assets/74eb9b2e-7f46-40bd-8c9c-646ad336e38d" />
> This Dockerfile is used to build the application frontend image using a multi-stage build approach. The first stage builds the React/Node.js v16 application, while the second stage uses Nginx to serve the build results as a static web, making the image lighter and ready to run in a production environment.

> <img width="1790" height="62" alt="image" src="https://github.com/user-attachments/assets/ce4b794f-404e-425d-a9ad-411414b8d601" />
> the result of images that have been created based on the previous Dockerfile

> <img width="1882" height="960" alt="image" src="https://github.com/user-attachments/assets/6557d203-1bbe-4e6b-9520-20ab9c42cd41" />
> <img width="1885" height="896" alt="image" src="https://github.com/user-attachments/assets/0d588d5b-b7be-46dc-9120-d6591ee1d84e" />
> <img width="1892" height="860" alt="image" src="https://github.com/user-attachments/assets/998972e3-cde8-420c-9e47-363d8f038ddc" />
> <img width="1881" height="399" alt="image" src="https://github.com/user-attachments/assets/8ce65705-60b2-4457-99c1-998950c314f3" />
> This file defines a Jenkins-based frontend CI/CD pipeline. The pipeline will run automatically when there is a push to GitHub, perform code quality analysis using SonarQube, pull the latest code according to the branch, build a Docker image, stop old containers, run new containers based on the branch (staging/production), and perform health checks with wget spider to ensure the application is running properly.

> <img width="1793" height="344" alt="image" src="https://github.com/user-attachments/assets/7c16cf32-d863-4625-9274-44132f74a4e7" />
> results from checking using wget spider 

> <img width="1919" height="1056" alt="image" src="https://github.com/user-attachments/assets/bb81ec23-ecdf-4da5-bec2-47ab68b84d24" />
> results after successfully deploying the frontend







# Section Heading 

Some body text of this section.

<a name="my-custom-anchor-point"></a>
Some text I want to provide a direct link to, but which doesn't have its own heading.

(… more content…)

[A link to that custom anchor](#my-custom-anchor-point)
