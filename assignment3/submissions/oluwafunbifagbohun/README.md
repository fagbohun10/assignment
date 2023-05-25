## My name is oluwafunbifagohun and please file below my submission




Kubernetes, Docker, Containerisation and Virtualisation


What is a hypervisor and where does it sit in the server virtualisation stack?

Answer

A hypervisor, also known as a virtual machine monitor (VMM), is a software or firmware component that enables server virtualization. It allows multiple virtual machines (VMs) to run on a single physical server by abstracting and managing the underlying hardware resources.

The hypervisor sits at the lowest level of the server virtualization stack, directly above the physical hardware. It interacts with the server's hardware, including the CPU, memory, storage, and network interfaces, and provides a layer of virtualization that allows the creation and management of virtual machines.

There are two main types of hypervisors:

Type 1 or Bare-Metal Hypervisors: These hypervisors run directly on the physical hardware without the need for an underlying operating system. They have direct access to the hardware resources, providing high performance and efficiency. Examples of type 1 hypervisors include VMware ESXi, Microsoft Hyper-V, and Citrix XenServer.

Type 2 or Hosted Hypervisors: These hypervisors run on top of a host operating system. The host operating system manages the hardware resources and provides services to the hypervisor and virtual machines. Type 2 hypervisors are typically used in desktop or workstation virtualization scenarios. Examples of type 2 hypervisors include VMware Workstation, Oracle VirtualBox, and Microsoft Virtual PC.

The hypervisor allows the creation, provisioning, and management of virtual machines. It allocates hardware resources to each VM, isolates them from one another, and ensures their smooth operation. The hypervisor also facilitates features such as virtual machine migration, snapshotting, and resource allocation.

Above the hypervisor layer, there are additional software components that form the server virtualization stack, such as management software, virtualization APIs, orchestration tools, and application software running within the virtual machines. These components work together to provide a complete virtualization solution.




What is a container runtime and name the two most common runtimes?
Linux administration and shell scripting

Answer


A container runtime is a software component that creates and runs containers. It is responsible for loading container images from a repository, monitoring local system resources, isolating system resources for use of a container, and managing container lifecycle.

The two most common container runtimes are:

Docker: Docker is a popular container runtime that is easy to use and has a large community of users.
Kubernetes: Kubernetes is a container orchestration system that can manage multiple container runtimes.
Other popular container runtimes include:

CRI-O: CRI-O is a lightweight container runtime that is designed to be integrated with Kubernetes.
Podman: Podman is a container runtime that is similar to Docker, but it is not tied to any specific container image format.
runC: runC is a lightweight container runtime that is designed to be used as a building block for other container runtimes.
Container runtimes are an important part of the container ecosystem. They provide the foundation for running containers and managing container lifecycle.

Here are some additional details about the two most common container runtimes:

Docker

Docker is a popular container runtime that is easy to use and has a large community of users. Docker provides a number of features that make it easy to create, run, and manage containers, including:

A simple command-line interface for creating and managing containers
A registry for storing and sharing container images
A Dockerfile format for defining container images
Kubernetes

Kubernetes is a container orchestration system that can manage multiple container runtimes. Kubernetes provides a number of features that make it easy to scale and manage containerized applications, including:

A scheduler for automatically assigning containers to hosts
A load balancer for distributing traffic to containers
A health checker for monitoring container health
Kubernetes is a complex system, but it can provide a number of benefits for organizations that are running containerized applications.

Sources
medium.com/@inder-devops/its-time-to-migrate-your-container-runtime-kubernetes-1-24-is-coming-f0c0b6b9bb90



Linux administration and shell scripting

Use just one command to create a directory structure where the directory sports contains a directory called footballteams which itself contains africanteam which itself contains pwdkumba.


Answer



Use the tree command to display your directory structure.
Research the following linux commands a) grep b) sed c) awk
CICD, Git, GitHub, GitHub Action, Infrastructure as as Code (IaC), Terraform, Packer and Ansible
You create a repository in GitHub called myfirstrepo. You then clone this repository on your local laptop. On your laptop how would you check its remote address? How would you go about changing the remote address so that it points to repository called mysecondrepo?
You have a workflow running on GitHub Action that has the following code;
jobs:
  deploy_to_production:
    runs-on: ubuntu-latest
    name: deploy to production with soruce code
    steps:
      - name: Checkout GitHub Action
        uses: actions/checkout@v2

      - name: Login via Azure CLI
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: deploy to production step with soruce code
        uses: azure/spring-cloud-deploy@v1
        with:
          azure-subscription: ${{ env.AZURE_SUBSCRIPTION }}
          action: deploy
          service-name: <service instance name>
          app-name: <app name>
          use-staging-deployment: false
          package: ${{ env.ASC_PACKAGE_PATH }}
Describe what you think this code is doing.

System Architecture and Application Design, Cloud Computing (AWS)
You have worked thus far with systems that you have had to download and install on your local laptop as well as systems hosted remotely on some external cloud. Describe in details the features and capabilities of all the systems (local and remote) that you have worked with thus far on this training. Draw a solution architecture diagram depicting these systems and where they fit in your solution landscape.
For all the systems that you have installed locally, write a manual for its installation and configuration.
In a general manner describe would you would interact with AWS account
AWS provide a public and a private area in which you could deploy your services. In which of these would you deploy the following services? a) EC2 instances b) DynamoDB databases c) VPC network d) S3 buckets e) IAM users
Site Reliability Engineering (SRE), Troubleshooting, Observability
Research on what APM (application programming monitoring)
What is a system metric and why might it be useful to collect metrics?
What is an system log and why might you want to collect logs?
DevOps and Agile Transformation principles and methodology
Communication, Collaboration and Automation and key aspects of a successful DevOps implementation. Describe why these traits are important in a DevOps transformation process.
You work for an organisation that is very keen to make their work visible across the organisation. What do you understand by this and how would you suggest they go about it?
New commands logs - Enter up to ten new commands you have learnt this week
Number	Commands	What does it do and how might you check its effect
1	XXXXXXXX	YYYYYYYY
2	XXXXXXXX	YYYYYYYY
3	XXXXXXXX	YYYYYYYY
4	XXXXXXXX	YYYYYYYY
5	XXXXXXXX	YYYYYYYY
6	XXXXXXXX	YYYYYYYY
7	XXXXXXXX	YYYYYYYY
8	XXXXXXXX	YYYYYYYY
9	XXXXXXXX	YYYYYYYY
10	XXXXXXXX	YYYYYYYY
Glossary of the week - Enter new technical words you have learnt this week and their meanings.
Number	Word	Meaning
1	XXXXXXXX	YYYYYYYY
2	XXXXXXXX	YYYYYYYY
3	XXXXXXXX	YYYYYYYY
4	XXXXXXXX	YYYYYYYY
5	XXXXXXXX	YYYYYYYY
6	XXXXXXXX	YYYYYYYY
7	XXXXXXXX	YYYYYYYY
8	XXXXXXXX	YYYYYYYY
9	XXXXXXXX	YYYYYYYY
10	XXXXXXXX	YYYYYYYY
