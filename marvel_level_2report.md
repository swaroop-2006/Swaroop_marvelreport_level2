# Swaroop's CLCY Level-003 Course work

# Level-3 Final Report


## Task 3 : SSH

ssH  is a newtwork protocol wher we can get access to a remote system just by using keys here ther are mainly two systems client and the server the client can access the remote server with the help of keys present in local storege here client has two keys private and publickey and server has public key now the client share the publickey and the server cheks the key and sends an encrypted file which is decrypted by using the private key pressent in the local system which sends back the result in encrypted form to the server now server checks the file and gives the connection.

difficulty i have faced in the task 
<div>
1.i was using 2 vm's here kali and ubantu one of which was in nat and other was in bridged adapter so they couden't connet so i replace  the system which was attached to nat to bridge adapter i used ping command to check if the system is reachable 
<div>
The command i used in the whole task
command for both server and client
sudo apt update
<div>
command for server
sudo apt install openssh-server
sudo systemctl status ssh
sudo systemctl start ssh
sudo systemctl enable ssh
ip addr
<div>
command for client 

ssh keygen -t ed25519

ssh-copy-id -i ~/.ssh/id_ed25519.pub username_ofserver@host_ipaddress

ping server_ipadress

ssh -i ~/.ssh/mykey  user_is@host_ipaddress

after gaining the remote access of the server 

i checked all the directories using ls command then created a directiry marvelclcytask using mkdir command the created a file in it using touch command then i verified them all by entering into kali linux and checking the directory. 

attachements 
<a href="https://ibb.co/MDnmBWLx"><img src="https://i.ibb.co/Gv7qHBj4/IMG-20260716-121754.jpg" alt="IMG-20260716-121754" border="0"></a>
<a href="https://ibb.co/GfjfKCV3"><img src="https://i.ibb.co/RGWGxQC4/IMG-20260716-121813.jpg" alt="IMG-20260716-121813" border="0"></a>
<a href="https://ibb.co/HLXBRBpT"><img src="https://i.ibb.co/V03JbJpY/IMG-20260716-121831.jpg" alt="IMG-20260716-121831" border="0"></a>

## Task 5 : Wireshark

# Wireshark – Lecture Summary

Wireshark is an open-source network packet analyzer used to capture and analyze network traffic. It only monitors packets and does not alter their flow.

### Lecture 1 – Wireshark Basics

* Applied **coloring rules** to identify TCP/Sky protocol packets separately.
* Changed Wireshark's **interface layout** through Preferences.
* Added and named a custom **Delta** column to analyze packet timing.
* Checked the **network diagram**.
* Increased the **user-interface size** for better visibility.

### Lecture 2 – Interfaces & Packet Storage

* Learned how to **manage network interfaces**.
* Saved captured traffic in **PCAPNG** format.
* Limited capture storage to **500 MB**.
* Learned about **ring buffers**, which allow captured data to be distributed across multiple files.

### Lecture 3 – Wireshark CLI

* Added Wireshark tools to the **system PATH**.
* Accessed Wireshark capture tools through the **Command Line Interface**.
* Learned `dumpcap` commands:

  * `dumpcap -h` – Display help.
  * `dumpcap -i` – List interfaces.
  * `dumpcap -w` – Specify the output file.
  * `dumpcap -b` – Configure a ring buffer.
  * `-b filesize` and `-b files` – Set file size and number of files.

### Lecture 4 – Network Monitoring


* Understood that Wireshark is used to **capture and analyze network traffic**.

### Lecture 5 – Filtering

Learned the difference between:

* **Capture filters** – Filter packets while capturing.
* **Display filters** – Filter already captured packets.

Examples: `ip.addr`, `tcp.port`, `frame contains`, `matches`, `in`, and `not`. Filters can also be applied by right-clicking a packet.

### Lecture 6 – Name Resolution

* Learned **name resolution**.
* Converted IP addresses into readable names.
* Reloaded packet captures using different formats/options.

### Lecture 7 – Time Analysis

* Added **time and date** information to packet columns.
* Used **time references** to measure how long operations took between packets.
* Learned how to remove/unset time references.


### Lecture 8 – File Extraction

* Learned how to **extract files from unencrypted PCAP captures**.


<a href="https://ibb.co/S4Yp0QXB"><img src="https://i.ibb.co/rR8JMbGH/Screenshot-43.png" alt="Screenshot-43" border="0"></a>



## Task 9 : Hashing 

Hashing is a process of storing password in the form of hashes which is uni directional means whcich can't be decrypted .so how can we verify? the alogrithem convert the password into hashes and compares it with uses password which is converted in hashes if they match then login is succesful or else it fails .It uses cryptographic functions like MD5 and SHA1 ,it protects the password from hackers (even if they have access to database).Even this method is not 100% secure but it slow down the hacker (he need to spend more money and time).

here is the program on hashing by using hashlib 

<a href="https://ibb.co/C33vJ7jV"><img src="https://i.ibb.co/5ggvY8Qs/Screenshot-46.png" alt="Screenshot-46" border="0"></a>

<a href="https://ibb.co/23XD7Fnd"><img src="https://i.ibb.co/jk7cv86D/Screenshot-45.png" alt="Screenshot-45" border="0"></a>

## Task 2 : Jenkins

jenkins is a open-source automation server which is used for  ci/cd pipeline .
CI-continous intigration (when organization is workin on a large project the every one merge their code to their designated branch without any conflict which can be done by CI)
CD - all the code after succesfully merging into the main branch it is ready for deployment so the new as new versions come for the product it should be deliverd to end customers which can be done by CD.

Stages in my pipeling
checkout
build 
test

in this task i used jenkins to chekout ,build and test static webpage . Initially i created a Jenkinfile which contain the script of the pipeline in the same folder as webpage.Then i built an image of jenkins and ran the jenkins container using the command docker run -d --name jenkins -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts here "-d" is for detaching jenkins (to make it run in background) . i enterd the adminstrator password and filled the credentials then i created job clicked on pipelines then selected and selected defination as pipeline script from scm,scm as git ,pased the url of my repository in repository url,branch specifier as /main as i am working in this branch finally script path as jenkinsfile.

after ran the job and it was successful 

1. Source Code Stage
Developers write new features or bug fixes.
Code is stored in a Git repository (GitHub, GitLab, etc.).
Every change is tracked through commits.
Team members can collaborate on the same project.
A push to the repository usually triggers the CI/CD pipeline.
2. Build Stage
Source code is compiled or packaged.
Dependencies are downloaded and resolved.
Syntax and compilation errors are detected.
Docker images or application packages are created.
Produces a deployable artifact.
3. Test Stage
Runs unit tests on individual functions/modules.
Runs integration tests between components.
Checks whether recent changes broke existing features.
Provides automatic pass/fail results.
Prevents faulty code from moving forward.
4. Staging Deployment Stage
Deploys application to a test environment.
Mimics production as closely as possible.
Verifies deployment scripts work correctly.
Allows testing before public release.
Helps identify environment-specific issues

<a href="https://ibb.co/tTtfNtF1"><img src="https://i.ibb.co/jP2Kx2sj/Screenshot-51.png" alt="Screenshot-51" border="0"></a>

<a href="https://ibb.co/bMy4yLwz"><img src="https://i.ibb.co/LXqTq6jn/Screenshot-50.png" alt="Screenshot-50" border="0"></a>

<a href="https://ibb.co/RpvFdpd7"><img src="https://i.ibb.co/SXsjGXGJ/Screenshot-49.png" alt="Screenshot-49" border="0"></a>

<a href="https://ibb.co/0PNNjGX"><img src="https://i.ibb.co/1HVVfmn/Screenshot-48.png" alt="Screenshot-48" border="0"></a>

## Task 4:Teraform
Terraform is an Infrastructure as Code (IaC) tool developed by HashiCorp Terraform  that allows you to create and manage infrastructure using code. It uses configuration files written in HashiCorp Configuration Language (HCL) to define resources such as virtual machines, networks, and storage. Terraform can work with multiple platforms including AWS, Azure, Google Cloud, Docker, and Kubernetes through providers. It follows a workflow of  init → plan → apply → destroy  to provision and manage infrastructure. By automating infrastructure management, Terraform makes deployments consistent, repeatable, and easier to version-control using Git.

terraform init

Initializes the Terraform project and downloads the required providers (such as AWS or Docker). It prepares your working directory so Terraform can communicate with the target platform.

terraform plan

Analyzes your configuration and shows what resources will be created, modified, or deleted. It lets you review changes safely before making them.

terraform apply

Executes the actions shown in the plan and creates or updates the infrastructure. Terraform then saves information about the resources in the state file.

terraform destroy

Deletes all infrastructure resources managed by the current Terraform configuration. It is commonly used for cleanup after testing or when resources are no longer needed.


<a href="https://ibb.co/4w1hK4SY"><img src="https://i.ibb.co/ZR2qGcgY/Screenshot-52.png" alt="Screenshot-52" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'>create image album</a><br />

<a href="https://ibb.co/6csC2NsV"><img src="https://i.ibb.co/bjd9x7dq/Screenshot-53.png" alt="Screenshot-53" border="0"></a>

<a href="https://ibb.co/JW0JMrDF"><img src="https://i.ibb.co/p6GF94Yr/Screenshot-54.png" alt="Screenshot-54" border="0"></a>

<a href="https://ibb.co/fGBjcqCC"><img src="https://i.ibb.co/Pz3qSF55/Screenshot-55.png" alt="Screenshot-55" border="0"></a>

<a href="https://ibb.co/XkdzzkG2"><img src="https://i.ibb.co/NnkLLnGV/Screenshot-56.png" alt="Screenshot-56" border="0"></a>

## Task 6 : Docker 

Docker is a software framework  which is used to building ,running  and manage containers on the servers or cloud 

Docker image is a lightweight ,standalone exicutable packge of software which includes every thing needed to run an application:

Docker container is a standard unit of software which contains code ,dependencies and required libraryes all wrapped in one so that it can work quickly and relably in different environment

The commands i used in this task:
1.docker build -t my-website .
2.docker images 
3.docker rmi image-id
4.docker run -d -p 8089:80 my-website 
5.docker ps -a 
6.docker rm containerid or name
7.docker start containder id or name

## Task 8 :Web Scraping and automation (flight ticket price analysis)

Web Scraping is a technique that helps in process of extracting data or content from websites using various libraries of python. Throughout the task, the errors were challenging and learning steps like real flight websites failed due to modern SPA design, controlled inputs, and anti-bot mechanisms also issues included city values not storing, search not triggering, wrong data extraction, slow loading, and ChromeDriver misconfiguration but these were solved by inspecting the DOM, fixing ChromeDriver setup, and refining element selectors thus a Selenium-friendly demo site was used to ensure reliable automation and dynamic scraping and learnt the importance of proper environment setup, DOM analysis, and choosing suitable websites for automation tasks.

<a href="https://ibb.co/4nLkjTJC"><img src="https://i.ibb.co/NdqRLj7f/Screenshot-20261004-134531.jpg" alt="Screenshot-20261004-134531" border="0"></a><br /><a target='_blank' href='https://dedupelist.com/'>dedupe subscriber list online</a><br />

## Task 1 :AWS LAMBDA

AWS Lambda is a serverless compute service that runs code in response to events without requiring you to manage servers. In this task I deployed an anonymous ID-based messenger using a single Python Lambda function exposed through a Function URL. The function serves the web page and handles sending and receiving messages, storing them in a DynamoDB table with a TTL so they auto-delete after 24 hours. I configured the handler, an environment variable, and an IAM policy giving the function least-privilege access to the table. This showed how Lambda removes the need to provision or scale servers.

## Task 7: Dockerize ( without using yaml file )

In this task, I containerized my task manager web application, which has an HTML/CSS/JS frontend, a Node.js and Express backend, and a MySQL database. I wrote a Dockerfile for the backend that uses the node:20-alpine base image, sets the working directory, installs dependencies with npm install, copies the application code, exposes port 3000, and starts the server with node server.js. I built this into a custom image using the docker build command. A separate frontend Dockerfile was not needed because the Express backend serves the frontend files. For the database, I pulled the official mysql:8.0 image. I then created a custom bridge network named task-net and a named volume called task-db-data. I ran both containers using only Docker CLI commands, without docker-compose or YAML files. The database container was attached to the network and the volume, which is mounted at /var/lib/mysql, and the backend container joined the same network, with port 3000 published to the host. The backend connected to the database by its container name, using environment variables for the host, user and password. I verified the setup by using the application in the browser, querying the data inside the database container, and inspecting the network and volume. I also deleted and recreated the database container to confirm that the data persisted. This task helped me understand Dockerfiles, images, containers, networking, environment variables and the importance of volumes for persistent storage.

DOCKER COMMANDS USED IN THE TASK

1. Build the backend image
docker build -t task-backend .

2. Pull the database image
docker pull mysql:8.0

3. Create the network and volume
docker network create task-net
docker volume create task-db-data

4. Run the database container
docker run -d --name task-db `
  --network task-net `
  -v task-db-data:/var/lib/mysql `
  -v "${PWD}\schema.sql:/docker-entrypoint-initdb.d/schema.sql" `
  -e MYSQL_ROOT_PASSWORD=Task12345 `
  mysql:8.0

5. Run the backend container
docker run -d --name task-backend `
  --network task-net -p 3000:3000 `
  -e DB_HOST=task-db -e DB_USER=root -e DB_PASSWORD=Task12345 -e DB_NAME=taskdb `
  task-backend

Open http://localhost:3000

6. Check the data in the database
docker exec -it task-db mysql -uroot -pTask12345 taskdb
SHOW TABLES;
SELECT * FROM tasks;
exit

7. Start, stop and clean up
docker start task-db task-backend
docker stop task-backend task-db
docker rm -f task-backend task-db
docker network rm task-net
docker volume rm task-db-data

## TASK 10:N-MAP

NMap or the Network Mapper scans networks to find live hosts, open ports, running services and operating systems, helping us map networks, find vulnerabilities, and manage services by sending specially crafted packets and analyzing responses. We did various analysis with NMap which includes identifying open ports and running services on a system, detecting the operating system using network behavior and etc. The Nmap aggressive scan that was taken identified multiple open ports associated with Windows system services and local web applications. Ports 135 and 445 indicate Windows RPC and SMB services, while ports 8080 and 9001 indicate HTTP-based services including a Jetty web server. OS detection successfully identified the host as Microsoft Windows 10. The scan results were saved and analyzed to assess potential security exposure.