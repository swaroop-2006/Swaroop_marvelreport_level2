# Swaroop's CLCY Level-003 Course work

# Level-3 Final Report

## Task 1: AWS Lambda

AWS Lambda 

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

## Task 5 : Wireshark

Wireshark is a opensource network-packet analyzer which monitors the flow of packets in a network cable (i dosen't add or altet the flow of any packet).

first lecture i learnt about thes points
1.How can i seperate tcp sky protocol from others by using different colour

2.Changing the layout of  the wireshark in propeties option  

3.Adding  colum and naming it delta

4.Checking the network diagram 

5.Increasing the size of user interface

second lecture i learnt about 

1.How can i manage interfaces in wireshark

2.Storing the output in pcapng file (i limited the storage of the file to 500mb)

3.learnt about ring buffer(limit of how many files it can create)

third lecture on wireshark 

1.I learnt about how to add wireshark to the path

2.learnt about how can we access wire shark from command line interface

3.learnt about commands like       
     dumcap -h for help
     dumcap -i for interfaces
     dumcap -w for giving the location to the file in wich it stores the interface data
     dumcap -b for ring buffer
    -b filesize -b files

4th lecture i learnt about

1.where to install wireshark in ideal case  (near tap or span)

2.what is vtap and vspan (what is tap and span)

3.we download wireshark to analyze traffic 

in the fifth lecture i learnt about 

1.what is and how to create capture filter?

2.what and how to create display filter
ip.adress eq,not (),tcp.port in {,,},right click filtering,frame contains or matches string.

basicaly this lecture was based on filtaring data

lecture 6 
 
 i learnt about name resolution
 2.changed the ip adress of the sourse to a name called sourse
 3.reloded the file in different format

 lecture 7

 it was about time 
 1.You can add time and date in time colum
 2.if you want to make a packet reference to know time taken by other packets to do that can be seen here
 3.how to unset all time refrence by using edit

 lecture 8

1.hear learnt about how can we read pcaps with wireshark

2.using statirstics in wireshark

3.should watch newer video so that i can get trace file.

lecturen 9 

1.It was about how to extract files from pcaps (unencrypeted one)

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

