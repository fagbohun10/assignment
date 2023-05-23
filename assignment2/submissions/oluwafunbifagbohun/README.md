## My name is oluwafunbi fagbohun and please file below my submission of assigment2 which was completed in collaboration with Abiodun and Emmanuella

## Kubernetes, Docker, Containerisation and Virtualisation

1)  Containers and virtual machines are both popular approaches to deploying applications, each with its own advantages and disadvantages:

Advantages of Containers:

1. Lightweight: Containers are more lightweight compared to virtual machines because they share the host OS kernel. They consume fewer system resources, making them faster to start, stop, and scale.

2. Efficient resource utilization: Containers can be packed more densely on a host system, allowing for better utilization of resources.

3. Faster deployment and scaling: Containers can be created, deployed, and scaled quickly, enabling faster application development cycles and easier horizontal scaling.

4. Isolation: Containers provide process-level isolation, ensuring that applications and their dependencies are encapsulated and isolated from each other, enhancing security and stability.

Disadvantages of Containers:

1. Limited OS support: Containers rely on the host OS kernel, which means they can only run on operating systems compatible with the container runtime.

2. Limited application compatibility: Some applications may have dependencies or requirements that are difficult to package into containers or may not work well in a containerized environment.

Advantages of Virtual Machines:

1. Full OS isolation: Virtual machines provide complete OS isolation, allowing different operating systems to run on the same physical hardware. This flexibility enables running legacy or incompatible software.

2. Robust security: Virtual machines offer strong isolation between guest operating systems, making them suitable for hosting applications with high-security requirements.

3. Hardware-level abstraction: Virtual machines abstract the underlying hardware, making them portable across different host systems.

Disadvantages of Virtual Machines:

1. Higher resource overhead: Virtual machines require a dedicated guest OS and associated resources, resulting in higher resource overhead compared to containers.

2. Slower start-up and scaling: Virtual machines take longer to start and require more time to scale due to the need to boot a full operating system.

3. Limited density: Virtual machines consume more resources and have more significant performance overhead, limiting the number of virtual machines that can be hosted on a single physical server.

In summary, containers are advantageous for lightweight, fast, and efficient deployments, while virtual machines offer greater flexibility in terms of operating system support and security isolation. The choice between containers and virtual machines depends on specific application requirements, resource constraints, and compatibility needs.


2)
A Docker image is a lightweight, standalone, and executable package that contains everything needed to run a piece of software, including the code, runtime, libraries, dependencies, and system tools. Docker images are built based on instructions provided in a Dockerfile.

Here's a high-level overview of the process of creating a Docker image:

1. Create a Dockerfile: A Dockerfile is a text file that specifies the instructions to build the Docker image. It typically starts with a base image that serves as the starting point.

2. Define the desired image structure: In the Dockerfile, you define the configuration, dependencies, and steps to set up the environment required for your application.

3. Specify the instructions: The Dockerfile includes instructions to copy files into the image, install software packages, set environment variables, expose network ports, and define the commands to run when the container is started.

4. Build the Docker image: Use the docker build command to build the Docker image based on the instructions in the Dockerfile. During the build process, Docker executes each instruction, creating layers and caching intermediate results for faster subsequent builds.

5. Tag and push the Docker image (optional): After building the Docker image, you can tag it with a version or label using the docker tag command. If you want to share the image with others or deploy it to a container registry, you can use the docker push command to upload the image to a registry like Docker Hub or a private registry.

By following these steps, you can create a Docker image that encapsulates your application and its dependencies, making it portable and easy to distribute and deploy across different environments.


3) A Docker container is an isolated and lightweight runtime environment that encapsulates an application and its dependencies. It allows you to run applications consistently across different environments without worrying about differences in underlying infrastructure.

To run a Docker container, you follow these steps:

Pull the Docker image: If you haven't already, use the docker pull command to download the Docker image from a container registry. For example:

'docker pull image:tag'

Replace image:tag with the name and version (tag) of the Docker image you want to use.

2. Run the Docker container: Use the docker run command to start a container based on the Docker image. For example:

docker run [options] image:tag


Replace image:tag with the name and version (tag) of the Docker image you want to run. The [options] can include parameters such as port mapping, volume mounting, environment variables, and more.

3. Interact with the running container: Once the container is running, you can interact with it in various ways:

To view logs from the container, use the docker logs command.
To execute commands within the container, use the docker exec command.
To access a shell session inside the container, use the docker exec -it command.
4. Stop or remove the container: To stop a running container, use the docker stop command followed by the container ID or name. For example:


docker stop container_id

To remove a stopped container, use the docker rm command followed by the container ID or name. For example:

bash

docker rm container_id

These are the basic steps to run a Docker container. Docker provides a wide range of options and commands to manage containers, including scaling, networking, container orchestration, and more. By leveraging Docker's containerization technology, you can achieve consistent, portable, and efficient application deployments.







## Linux administration and shell scripting

1) Write a shell script that takes a single input arguments and echoes it back when it is run.

Certainly! Here's a simple shell script that takes a single input argument and echoes it back when executed:


#!/bin/bash

# Check if an argument is provided
if [ -z "$1" ]; then
  echo "Please provide an argument."
  exit 1
fi

# Echo the provided argument
echo "You entered: $1"


Save the above script into a file, such as echo_back.sh. Make the file executable using the following command in the terminal:


chmod +x echo_back.sh


To run the script, provide an argument when executing the script:

bash

./echo_back.sh Hello, World!
The output will be:

yaml

You entered: Hello, World!
If no argument is provided, it will display a message asking for an argument.



2) Write a shell script that creates a directory call "sports" and inside the "sports" directory create two other subdirectories called "football" and "handball". You should be able to run the script multiple times without it failing.



Certainly! Here's a shell script that creates a directory called "sports" and two subdirectories "football" and "handball" inside it. It ensures that the script can be run multiple times without failing:

bash


#!/bin/bash

# Set the parent directory name
parent_dir="sports"

# Check if the parent directory already exists
if [ ! -d "$parent_dir" ]; then
  # Create the parent directory
  mkdir "$parent_dir"
  echo "Created directory: $parent_dir"
else
  echo "Directory already exists: $parent_dir"
fi

# Create the subdirectories
subdirs=("football" "handball")
for subdir in "${subdirs[@]}"; do
  subdir_path="$parent_dir/$subdir"

  # Check if the subdirectory already exists
  if [ ! -d "$subdir_path" ]; then
    # Create the subdirectory
    mkdir "$subdir_path"
    echo "Created directory: $subdir_path"
  else
    echo "Directory already exists: $subdir_path"
  fi
done


Save the above script into a file, such as create_sports_directories.sh. Make the file executable using the following command in the terminal:

bash

chmod +x create_sports_directories.sh


To run the script, execute it:

bash

./create_sports_directories.sh


The script will create the "sports" directory if it doesn't already exist and create the "football" and "handball" subdirectories inside it. If the directories already exist, it will display a message indicating that they exist. Running the script multiple times will not result in errors or duplicate directories.


3) Copy the code below into a file called hello.sh and run it. Explain the behaviour.

#!/bin/bash
echo "You are using $(basename $0)"
for n in $*
do
    echo "Hello $n"
done
exit 0


The provided code is a shell script named hello.sh. Here's an explanation of its behavior:

#!/bin/bash: This is called a shebang and specifies the interpreter (in this case, /bin/bash) to execute the script.

echo "You are using $(basename $0)": This line outputs a message stating the script's name. basename $0 extracts the base name of the script file being executed.

for n in $*: This is a loop that iterates over the command-line arguments provided when executing the script. $* represents all the command-line arguments passed to the script.

echo "Hello $n": Within the loop, this line prints a greeting message followed by each argument passed to the script.

exit 0: This line explicitly specifies an exit code of 0, indicating successful execution of the script.

To execute the script:

Save the provided code into a file named hello.sh.
Make the file executable by running the following command in the terminal:
bash

chmod +x hello.sh
Run the script by executing the following command in the terminal:
bash

./hello.sh John Alice Bob
The script will output the following:

sql

You are using hello.sh
Hello John
Hello Alice
Hello Bob
The first line displays the script's name (hello.sh in this case). Then, for each command-line argument provided (John, Alice, and Bob in the example), it outputs a "Hello" message followed by the argument's value. Finally, it exits with a code of 0, indicating successful execution.


4)
Sure! Let's analyze the script "addme.sh" line by line:



#!/bin/bash
# (@)/ph
# A very simple telephone list
# Type "ph new name number" to add to the list, or
# just type "ph name" to get a phone number

These lines are comments that provide some information about the script and its usage.


PHONELIST=~/.phonelist.txt

This line defines a variable PHONELIST and assigns it the path ~/.phonelist.txt, which represents a file located in the user's home directory. It will be used as a storage location for the telephone list.


if [ $# -lt 1 ] ; then
    echo "Whose phone number did you want? "
    exit 1
fi


This if statement checks if the number of command-line arguments passed to the script ($#) is less than 1. If true, it means no command-line argument was provided, so it prompts the user with a message asking for the name of the person whose phone number they want. Then, it exits the script with a status code of 1.



if [ $1 = "new" ] ; then
    shift
    echo $* >> $PHONELIST
    echo $* added to database
    exit 0
fi


If the first command-line argument is equal to "new", this block of code executes. It uses the shift command to discard the "new" argument from the list of arguments. Then, it appends the remaining arguments ($*) to the PHONELIST file using >> redirection. It also prints a message indicating that the phone number has been added to the database. Finally, it exits the script with a status code of 0.

if [ ! -s $PHONELIST ] ; then
    echo "No names in the phone list yet! "
    exit 1
else
    grep -i -q "$*" $PHONELIST
    if [ $? -ne 0 ] ; then
        echo "Sorry, that name was not found in the phone list"
        exit 1
    else
        grep -i "$*" $PHONELIST
    fi
fi


If none of the previous conditions were met, this block of code is executed. It first checks if the PHONELIST file is empty or doesn't exist (-s checks if the file exists and is not empty). If true, it prints a message indicating that there are no names in the phone list yet, and exits the script with a status code of 1.

If the file is not empty, it uses grep to search for the provided argument ($*) case-insensitively (-i) in the PHONELIST file. The -q option makes grep operate in quiet mode, so it doesn't output anything. The script then checks the exit status of grep using $?. If the exit status is not equal to 0, it means the name was not found in the phone list. In that case, it prints an appropriate message and exits with a status code of 1.

If the name is found, it uses grep again without the -q option to perform a case-insensitive search and outputs the matching line(s) containing the name.


exit 0

This line indicates a successful exit from the script, with a status code of 0.

To run the script, follow these



5)  Certainly! Here's a script that fulfills your requirements:


#!/bin/bash

# Assign positional parameters to variables
ONE=$1
TWO=$2
THREE=$3

# Count the number of parameters
PARAMETER_COUNT=$#

# Combine all parameters into a single string
ALL_PARAMETERS="$*"

# Output the information
echo "There are $PARAMETER_COUNT parameters that include $ALL_PARAMETERS."
echo "The first is $ONE, the second is $TWO, the third is $THREE."
To run the script, follow these steps:

Copy the above script and save it into a file, for example, "param_info.sh".

Open a terminal and navigate to the directory where the script is located.

Make the script executable by running the command: chmod +x param_info.sh.

Run the script by executing: ./param_info.sh arg1 arg2 arg3, where "arg1", "arg2", and "arg3" are the values you want to pass as positional parameters. Feel free to adjust the number of arguments as needed.

The script will output the information in the specified format, replacing the placeholders with the actual values.

For example, if you run the script with the command ./param_info.sh apple banana cherry, the output will be:

csharp
Copy code
There are 3 parameters that include apple banana cherry.
The first is apple, the second is banana, the third is cherry.
The script takes three positional parameters and assigns them to variables ONE, TWO, and THREE. It then counts the number of parameters using $# and combines all parameters into a single string using "$*". Finally, it outputs the information using echo statements.





## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1) 1. Idempotence refers to the property of an operation where applying it multiple times produces the same result as applying it once. In the context of infrastructure provisioning or configuration management, idempotence means that running a provisioning or configuration operation multiple times will not cause any adverse or unintended effects. It ensures that the desired state is achieved regardless of the number of times the operation is executed.

2. Adopting a DevOps way of working brings several benefits to an organization, including improved collaboration and communication between development and operations teams, faster and more frequent software releases, increased efficiency and reliability of software delivery, enhanced automation and infrastructure scalability, better monitoring and feedback mechanisms, and a culture of continuous improvement and learning.

3. Provisioning infrastructure using tools like Terraform and Ansible offers benefits such as infrastructure-as-code, which allows for version control, reproducibility, and documentation of infrastructure configurations. It enables infrastructure to be treated as code, leading to better collaboration, consistency, and automation. These tools also provide a declarative approach, where the desired state of the infrastructure is defined, and the tools handle the necessary steps to achieve that state, resulting in easier management and scalability of infrastructure.

4. Tools based on agents, such as Chef and Puppet, have advantages like enhanced security and control, as the agents allow for continuous monitoring and enforcement of desired configurations on managed servers. Agents can also provide real-time data and insights about the managed servers. However, disadvantages include the need for agent installation and potential resource consumption on managed servers. Agents may also introduce dependencies and complexity in the infrastructure.

5. Mutable infrastructure refers to the traditional approach where servers or resources can be modified after they are provisioned. Immutable infrastructure, on the other hand, follows a design paradigm where servers or resources are considered immutable and any updates or changes are done by replacing the entire instance rather than modifying it. Immutable infrastructure design provides benefits such as improved security, easier scalability, simplified deployments, and easier rollbacks. Mutable infrastructure offers flexibility and ease of incremental updates but can be prone to configuration drift and inconsistency.

6. There are various commercial and enterprise tools available for different aspects of infrastructure provisioning and deployment. Some examples include AWS CloudFormation, Azure Resource Manager, Google Cloud Deployment Manager, Puppet Enterprise, Chef Automate, and Jenkins Enterprise. The choice of tool depends on the specific requirements, cloud platform, and the organization's existing infrastructure and processes.

7. Imperative provisioning refers to a step-by-step approach where explicit instructions are given to provision and configure infrastructure. It focuses on the detailed actions required to achieve a desired state. Declarative provisioning, on the other hand, involves specifying the desired end-state of the infrastructure without explicitly defining the steps to reach that state. Declarative provisioning tools, like Terraform, focus on defining the desired infrastructure configuration and handle the necessary actions internally to achieve that state.

8. GitHub Actions is a fully automated CI/CD integrated toolchain provided by GitHub. It allows developers to define workflows as code and automate various development and deployment tasks. GitHub Actions can be used to build, test, and deploy applications, as well as perform other custom actions based on triggers and events. It provides a flexible and customizable platform for implementing continuous integration and continuous deployment processes.

In the context of a provisioning pipeline, a Runner refers to a machine or compute resource that executes the tasks defined in a GitHub Action workflow. Runners can






## System Architecture and Application Design, Cloud Computing (AWS)

1. The flow of information in a provisioning pipeline comprising AWS, GitHub, your laptop, Terraform, and the Terraform state file stored in AWS typically follows these steps:

Development Environment (Your Laptop):

You write and manage the infrastructure code using Terraform on your laptop.
The infrastructure code is typically stored in a Git repository hosted on GitHub.
Source Code Management (GitHub):

The infrastructure code is version-controlled and stored in a Git repository on GitHub.
You can use Git commands or GitHub's web interface to manage the repository.
Continuous Integration (CI) and Version Control (GitHub Actions):

Whenever changes are made to the infrastructure code in the GitHub repository, GitHub Actions can be configured to trigger a workflow.
The workflow can include steps to validate, test, and build the infrastructure code.
Provisioning (AWS and Terraform):

After successful validation and testing in the CI workflow, Terraform is invoked to provision the infrastructure in AWS.
Terraform reads the infrastructure code from the GitHub repository.
Infrastructure Provisioning (AWS):

Terraform interacts with AWS to create and manage the necessary resources based on the infrastructure code.
AWS APIs are used to provision and configure resources such as EC2 instances, VPCs, subnets, security groups, etc.
Terraform State Management (AWS):

Terraform uses a state file to track the current state of the provisioned infrastructure.
The Terraform state file is stored in a backend, which in this case is an AWS service like Amazon S3 or Terraform Cloud.
The information flow in this architecture involves your laptop as the development environment where you write and manage the infrastructure code. The code is stored in a GitHub repository, which triggers a CI workflow in GitHub Actions when changes are made. After successful validation, Terraform is invoked to provision the infrastructure in AWS, using the infrastructure code from the GitHub repository. Terraform interacts with AWS to create and manage the resources, and the state file is stored in an AWS backend service.

Please note that this is a simplified representation of the architecture, and actual implementations may vary based on specific requirements and configurations.


2. he flow of information when cloning a public repository and pushing it to your own GitHub repository from your local laptop typically follows these steps:

Development Environment (Your Laptop):

You have a local development environment on your laptop where you run commands and interact with Git.
Source Code Management (GitHub):

The public repository you want to clone and your own GitHub repository are hosted on GitHub.
Cloning the Public Repository (Git Command):

Using Git commands on your local laptop, you clone the public repository from GitHub.
The clone command fetches a copy of the repository to your local machine.
Local Repository (Your Laptop):

After cloning, you have a local copy of the public repository on your laptop.
You can make modifications or perform any necessary actions on this local repository.
Pushing to Your GitHub Repository (Git Command):

Using Git commands, you push the cloned repository from your local laptop to your own GitHub repository.
This command transfers the changes you made locally to your GitHub repository.
Updated Repository (Your GitHub Repository):

After successfully pushing the changes, your own GitHub repository reflects the changes made in the public repository.
The repository now contains both the original content from the public repository and the modifications you made locally.
The information flow in this architecture involves your local laptop as the development environment, where you clone the public repository and make changes. The public repository and your own GitHub repository are hosted on GitHub. Using Git commands, you clone the public repository to your local machine and then push the changes to your own GitHub repository, updating its contents.


## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. To ensure the automated system for collecting metrics from the infrastructure using a third-party vendor's product does not cause unwanted effects, you can take the following steps:

Research and Understand the Vendor's Product:

Gain a good understanding of the vendor's product and its capabilities.
Review the documentation, user guides, and any available resources provided by the vendor.
Identify any potential risks or known issues associated with the product.
Test Environment:

Set up a separate test environment that closely resembles your production environment.
Deploy and configure the vendor's product in the test environment.
Verify that the metrics collection process works as expected in this isolated environment.
Perform thorough testing, including edge cases and stress testing, to identify any unexpected behavior or performance issues.
Backup and Recovery Mechanisms:

Implement robust backup and recovery mechanisms for your infrastructure.
Take regular backups of critical components, such as configuration files, databases, and relevant data.
Test the backup and recovery procedures to ensure you can revert to a stable state if any issues occur during the implementation or operation of the metrics collection system.
Rollout Plan:

Develop a rollout plan to implement the metrics collection system in a controlled manner.
Consider a phased approach, starting with a small subset of infrastructure or non-critical systems.
Monitor the impact of the system on performance, resource utilization, and other relevant metrics during each phase.
Gradually expand the deployment to cover the entire infrastructure while monitoring for any adverse effects.
Monitoring and Alerting:

Implement robust monitoring and alerting systems to proactively detect and respond to any issues or anomalies caused by the metrics collection system.
Set up relevant thresholds, alarms, and notifications to be alerted in real-time if any unwanted effects or performance degradation are observed.
Continuously monitor the infrastructure and metrics collected to identify any unexpected patterns or negative impacts.
By following these steps, you can minimize the risks associated with implementing the automated metrics collection system. Regular testing, backup mechanisms, controlled rollout, and monitoring will help ensure the system operates safely and avoids any unwanted effects.

Regarding running an unfamiliar script instructed by your manager, you can take the following approach to ensure safe execution:

Review the Script:

Inspect the script carefully to understand its purpose and functionality.
Check for any potential security vulnerabilities or risky operations within the script.
Pay attention to any external dependencies or resources the script interacts with.
Test in a Controlled Environment:

Set up a separate test environment, if possible, to execute the script without affecting production systems.
Verify the script's behavior and assess its impact in the test environment.
Validate the output and confirm that it aligns with the expected results.
Code Review and Peer Input:

Request a code review from a knowledgeable colleague or subject matter expert.
Discuss the script's purpose, potential risks, and any concerns you may have.
Gather feedback and insights to ensure the script's safety and effectiveness.
Take Precautions:

Make backups of critical systems and data before executing the script.
Consider executing the script in a sandboxed or isolated environment if it interacts with sensitive resources.
Implement proper permissions and access controls to limit the script's impact.
Monitor and Verify:

Observe the script's execution in real-time, if possible, and monitor for any unexpected behaviors or errors.
Validate the script's output against the desired outcome.
If the script performs changes, verify that they align with the intended results and do not introduce unintended consequences.
By following these precautions and steps, you can minimize the risks associated with running unfamiliar scripts and ensure







## DevOps and Agile Transformation principles and methodology

1. Version Control Systems:

Git (e.g., GitHub, GitLab, Bitbucket)
Configuration Management and Infrastructure as Code (IaC):

Ansible, Chef, Puppet
Terraform, AWS CloudFormation
Continuous Integration/Continuous Delivery (CI/CD):

Jenkins, GitLab CI/CD, CircleCI
Travis CI, Azure DevOps
Containerization and Container Orchestration:

Docker
Kubernetes, Docker Swarm, Amazon ECS
Cloud Platforms:

Amazon Web Services (AWS)
Microsoft Azure
Google Cloud Platform (GCP)
Monitoring and Logging:

Prometheus, Grafana
ELK Stack (Elasticsearch, Logstash, Kibana)
Splunk, Datadog
Collaboration and Communication:

Atlassian Suite (Jira, Confluence, Bitbucket)
Slack, Microsoft Teams

2. Online Job Boards and Platforms:

Explore popular job boards and platforms that specialize in remote work, such as Remote.co, We Work Remotely, and LinkedIn's remote job search feature.
Use search filters and keywords specific to DevOps to find relevant positions.
Networking:

Leverage your professional network, including contacts from previous jobs, colleagues, and online communities (such as DevOps-related forums, LinkedIn groups, and social media).
Attend industry events, meetups, and conferences, both online and in-person, to connect with potential employers and other professionals.
Freelance Platforms:

Consider joining freelancing platforms like Upwork, Freelancer, or Toptal, where you can find remote DevOps projects.
Create a compelling profile highlighting your skills and experience to attract clients.
Company Websites:

Visit the websites of companies you're interested in working for and look for remote DevOps positions in their career sections.
Some organizations may have a dedicated remote work policy or offer flexible work arrangements.
Remote Job Communities:

Engage with online communities focused on remote work, such as Slack channels, subreddits, or dedicated forums.
These communities often share job opportunities, insights, and tips for finding remote DevOps positions.
It's important to note that the availability of remote DevOps positions may vary based on factors such as location, industry, and the specific job market. Additionally, the article you referenced may offer additional strategies or insights that can be valuable in your search for remote DevOps gigs.





## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |
| :---        |    :----:   | :---  |
| 1  | chmod +x       | used to make a file executable. its stands for "change mode" and allows you to modify the permissions of a file or directory. |
| 2  | vim      |    | a popular text editor available in Unix-like operating systems.
| 4  | ls -ltr      |   it will display the file and directory listing in the following format:

-rw-r--r-- 1 user group 4096 May 1 12:30 file1.txt
drwxr-xr-x 2 user group 4096 May 2 09:45 directory1
-rw-r--r-- 1 user group 4096 May 3 14:20 file2.txt
| 3  | ls -la
| 5  | cd ../      |  it moves one level up in the directory hierarchy.   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | cp -R       | copy   |
| 2  | XXXXXXXX       | YYYYYYYY   |
| 3  | XXXXXXXX       | YYYYYYYY   |
| 4  | XXXXXXXX       | YYYYYYYY   |
| 5  | XXXXXXXX       | YYYYYYYY   |
| 6  | XXXXXXXX       | YYYYYYYY   |
| 7  | XXXXXXXX       | YYYYYYYY   |
| 8  | XXXXXXXX       | YYYYYYYY   |
| 9  | XXXXXXXX       | YYYYYYYY   |
| 10 | XXXXXXXX       | YYYYYYYY   |
