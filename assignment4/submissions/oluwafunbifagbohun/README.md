My name is Oluwafunbi fagbohun and kind see my submission for assignment4




## Key learnings, experience and your main selling points.

This section will be used to write your profile for your CV. So record your key learnings and experience on a weekly basis so we can track your progress and learning.

| Number      |           Subject              | What you have learnt this week and how might you describe this at an interview?   |
| :---        |            :----:              | :---  |
| 1  | Collaboration                           | Being able to share ideas and work with others.    
                                               Be respectful of others' ideas, even if you disagree with them.  |
| 2  | Communication                           | Be clear and concise in your communication.
                                                Be able to listen to others and understand their points of view.   |
| 3  | Automation/CICD                         |Learn about the different tools and technologies that are available for automation and                                              CI/CD.   |
| 4  | AWS                                     | Develop a cost-effective strategy for using AWS.  |
| 5  | Kubernetes                              | Develop a strategy for monitoring and troubleshooting your Kubernetes deployments.  |
| 6  | Terraform                               | Practice using Terraform to create and manage infrastructure as code.   |
| 7  | Linux                                   | Learn about the different commands and utilities that are available on Linux.  |
| 8  | System and Application Design           | Use system and application design to improve your scalability, reliability, and security.  |
| 9  | Productivity                            Use productivity tools and techniques to improve your efficiency and effectiveness.  |
| 10 | Yourself and your abilities             | Be willing to learn and grow.  |


## Kubernetes, Docker, Containerisation and Virtualisation

With respect to Kubernetes define what the following entities mean.

1) Pod: A pod is the smallest deployable unit of software in Kubernetes. A pod is a group of one or more containers that share resources and are scheduled together on the same node. Pods are the basic unit of isolation and scheduling in Kubernetes.
2) Container: A container is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries, and settings. Containers are isolated from each other and from the host machine, and they share the host's resources.
3) Node: A node is a physical or virtual machine that runs Kubernetes. Nodes are responsible for running pods and providing resources to pods. Nodes are managed by the Kubernetes control plane.
4) Control plane: The control plane is the brains of Kubernetes. It is responsible for managing the cluster, including scheduling pods, managing resources, and monitoring the health of the cluster. The control plane is made up of a set of components, including the kube-apiserver, kube-scheduler, kube-controller-manager, and etcd.
5) Data plane: The data plane is the part of Kubernetes that is responsible for running pods and providing resources to pods. The data plane is made up of the nodes in the cluster.

## Linux administration and shell scripting

1) You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that?
ans
Check the file permissions. Make sure that the file has the correct permissions for the user who is trying to run it. The most common permission for a shell script is 755, which means that the user who owns the file can read, write, and execute it, and other users can only read it.
Use the chmod command to change the file permissions. If the file permissions are incorrect, you can use the chmod command to change them. For example, to change the permissions of a file called addAccount.sh so that the user who owns it can read, write, and execute it, and other users can only read it, you would use the following command:
chmod 755 addAccount.sh

Run the script as root. If you are still having problems, you can try running the script as root. To do this, open a terminal and type the following command:
Code snippet
sudo ./addAccount.sh
Use code with caution. Learn more
Note: Running a script as root can be dangerous, so make sure that you trust the script before you do this.

If you have tried all of these things and you are still having problems, you may need to contact the person who wrote the script for help.

2) What Linux command would your use to find out what commands you have run in the past?

history
history | grep ls.


3) Research the following Linux commands
* chmod
* scp
* ssh
ans

chmod

The chmod command is used to change the permissions on files and directories. The permissions determine who can read, write, and execute the file or directory. The chmod command takes three arguments: the file or directory name, the permission mode, and the new permissions. The permission mode is a combination of three octal digits, each of which represents a different permission:

The first digit represents the permission for the owner of the file or directory.
The second digit represents the permission for the group that owns the file or directory.
The third digit represents the permission for everyone else.
The permissions can be either read (4), write (2), or execute (1). For example, to change the permissions on a file called myfile so that the owner can read and write it, and everyone else can only read it, you would use the following command:

Code snippet
chmod 644 myfile
Use code with caution. Learn more
The 6 in the permission mode represents the owner can read and write (4 + 2 = 6), and the 4 in the permission mode represents everyone else can only read (4).

scp

The scp command is used to securely copy files and directories between hosts. The scp command takes two arguments: the source file or directory, and the destination file or directory. The source file or directory can be on the local machine or on a remote machine. The destination file or directory must be on the local machine.

For example, to copy a file called myfile from the local machine to a remote machine called myserver, you would use the following command:

Code snippet
scp myfile myserver:myfile
Use code with caution. Learn more
The myserver part of the command is the hostname of the remote machine. You can also use the IP address of the remote machine.

ssh

The ssh command is used to securely connect to a remote machine. The ssh command takes two arguments: the hostname of the remote machine, and the username on the remote machine.

For example, to connect to a remote machine called myserver as the user myuser, you would use the following command:

Code snippet
ssh myuser@myserver
Use code with caution. Learn more
Once you are connected to the remote machine, you can use the shell to run commands. To disconnect from the remote machine, type exit.


## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. You want to use the following code to created an AWS EKS resource from the 
public repository pointed to by the source clause. How could you ensure
that any changes made to the public repository you are pointing to does not
adversely affect your infrastructure?

```
module "myeks" {
   source = "terraform-aws-modules/terraform-aws-eks"
   cluster_name = "mycluster"
}
```
ans

There are a few things you can do to ensure that any changes made to the public repository you are pointing to does not adversely affect your infrastructure:

Use a version control system. A version control system, such as Git, allows you to track changes to your code. This means that you can easily revert to a previous version of your code if a change made to the public repository breaks your infrastructure.
Use a staging environment. A staging environment is a copy of your production environment that is used for testing. This means that you can test changes to your code in a safe environment before deploying them to production.
Use a continuous integration/continuous delivery (CI/CD) pipeline. A CI/CD pipeline automates the process of building, testing, and deploying code. This means that you can quickly deploy changes to your code without having to worry about making mistakes.
By following these steps, you can help to ensure that any changes made to the public repository you are pointing to does not adversely affect your infrastructure.


2. When you run the terraform init command in the directory containing terraform files, what 
changes does it make to directory in which you run the command?


When you run the terraform init command in the directory containing Terraform files, it makes the following changes to the directory in which you run the command:

It downloads and installs any required providers.
It creates a .terraform directory, which contains the state file and other configuration files.
It creates a .terraform.lock.hcl file, which locks the version of each provider to the version that was downloaded.
The .terraform directory is the heart of a Terraform project. It contains all of the information that Terraform needs to manage your infrastructure. The .terraform.lock.hcl file ensures that Terraform always uses the same version of each provider, which can help to prevent unexpected changes to your infrastructure.

The terraform init command is a critical step in the Terraform workflow. It ensures that Terraform has everything it needs to manage your infrastructure.


3. What is the purpose of a Terraform provider?

ans


A Terraform provider is a plugin that allows Terraform to interact with a specific infrastructure provider, such as AWS, Azure, or Google Cloud Platform. Providers define the resources that can be created, updated, and deleted in the target infrastructure provider. They also define the parameters that can be used to configure those resources.

Terraform providers are available for a wide range of infrastructure providers. This makes it possible to use Terraform to manage infrastructure in a variety of environments.

When you use Terraform to manage infrastructure, you specify the provider that you want to use in your Terraform configuration file. Terraform will then download and install the provider if it is not already installed. Once the provider is installed, Terraform can interact with the target infrastructure provider to create, update, and delete resources.

Terraform providers are a powerful tool that can help you to automate the management of your infrastructure. They make it possible to use Terraform to manage infrastructure in a variety of environments, and they can help you to improve the consistency and reliability of your infrastructure deployments.

Here are some of the benefits of using Terraform providers:

Reusability: Providers can be reused across multiple Terraform projects. This can save time and effort when managing infrastructure.
Consistency: Providers ensure that Terraform always uses the same API to interact with the target infrastructure provider. This can help to prevent unexpected changes to your infrastructure.
Reliability: Providers can be tested and validated by the provider community. This can help to ensure that the provider is reliable and that it will work correctly with your infrastructure.
If you are using Terraform to manage infrastructure, I recommend that you use providers whenever possible. Providers can help you to improve the efficiency, consistency, and reliability of your infrastructure deployments.


4. What is the purpose of Terraform state?

The Terraform state file is a JSON file that stores information about the resources that Terraform has created or modified. This information includes the resource type, the resource name, and the resource configuration. The state file is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

The state file is stored in a local file by default, but it can also be stored in a remote location, such as a cloud storage service. Storing the state file in a remote location can make it easier to collaborate on infrastructure projects with other developers.

The state file is an important part of the Terraform workflow. It is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

Here are some of the benefits of using the Terraform state file:

Track changes to infrastructure: The state file tracks changes to your infrastructure. This can be helpful for debugging problems or for rolling back changes.
Ensure infrastructure is in desired state: The state file ensures that your infrastructure is always in the desired state. This can help to prevent unexpected changes to your infrastructure.
Easier collaboration: The state file can be stored in a remote location, such as a cloud storage service. This can make it easier to collaborate on infrastructure projects with other developers.


5. How would you ensure that the Terraform state is secure and can be used in a collaborative
environment with the rest of your team without it being corrupted?


Here are some tips on how to ensure that the Terraform state is secure and can be used in a collaborative environment with the rest of your team without it being corrupted:

Use a version control system: A version control system, such as Git, can be used to track changes to the Terraform state file. This makes it easy to revert to a previous version of the state file if it is corrupted.
Encrypt the Terraform state file: The Terraform state file can be encrypted to protect it from unauthorized access. This can be done using a variety of tools, such as HashiCorp Vault or AWS KMS.
Store the Terraform state file in a secure location: The Terraform state file should be stored in a secure location, such as a cloud storage service. This will help to protect it from unauthorized access.
Use a locking mechanism: A locking mechanism can be used to prevent multiple users from accessing the Terraform state file at the same time. This can help to prevent corruption of the state file.
Use a backup: A backup of the Terraform state file should be created and stored in a secure location. This will help to protect the state file in case of corruption or accidental deletion.


6. You have created a resource using Terraform. A colleague of your accidentally changed the resource
on the AWS console. What would happen if you run the Terraform apply command again?

ans


If you run the Terraform apply command again, it will try to create or update the resource in AWS to match the configuration in the Terraform configuration file. If the colleague of your has made changes to the resource in the AWS console, then running the apply command will overwrite those changes.

To avoid this, you can use the Terraform plan command to see what changes will be made before running the apply command. The plan command will show you a list of all the resources that will be created or updated, as well as the changes that will be made to each resource. You can then decide whether or not to proceed with the apply command.

You can also use the Terraform lock command to prevent other users from making changes to the resource while you are working on it. The lock command will prevent other users from using the state file, which will prevent them from making changes to the resource.

Finally, you can use the Terraform force command to force Terraform to overwrite any changes that have been made to the resource in AWS. However, you should only use the force command if you are sure that you want to overwrite the changes.

Here are some additional tips on how to avoid this situation:

Use a version control system: A version control system, such as Git, can be used to track changes to your Terraform configuration file. This makes it easy to revert to a previous version of the configuration file if it is accidentally overwritten.
Use a locking mechanism: A locking mechanism can be used to prevent multiple users from accessing the Terraform state file at the same time. This can help to prevent accidental overwriting of the state file.
Use a backup: A backup of the Terraform state file should be created and stored in a secure location. This will help to protect the state file in case of accidental overwriting or corruption.
By following these tips, you can help to avoid accidentally overwriting your Terraform state file.


7. You have a Terraform file in which you have defined 10 resources. You realise that one of the resources 
is no longer required. How would you go about deleting the unwanted resource without deleting the other resources?

ans


here are a few ways to delete an unwanted resource in Terraform.

Method 1: Delete the resource block from the Terraform configuration file

The simplest way to delete an unwanted resource is to delete the resource block from the Terraform configuration file. For example, if you have a Terraform configuration file that defines 10 resources, and you want to delete the resource named my_resource, you would delete the following resource block from the configuration file:

Code snippet
resource "my_resource" "my_resource" {
  # resource configuration
}
Use code with caution. Learn more
Once you have deleted the resource block from the configuration file, you can run the terraform apply command to delete the resource from your infrastructure.

Method 2: Use the terraform destroy command

If you don't want to edit the Terraform configuration file, you can use the terraform destroy command to delete the resource. The terraform destroy command takes the name of the resource as an argument. For example, to delete the resource named my_resource, you would run the following command:

Code snippet
terraform destroy my_resource
Use code with caution. Learn more
The terraform destroy command will prompt you to confirm that you want to delete the resource. Once you have confirmed, Terraform will delete the resource from your infrastructure.

Method 3: Use the terraform plan command

If you want to see what changes will be made before you delete the resource, you can use the terraform plan command. The terraform plan command will show you a list of all the resources that will be deleted, as well as the changes that will be made to each resource. You can then decide whether or not to proceed with the terraform destroy command.

For example, to see what changes will be made if you delete the resource named my_resource, you would run the following command:

Code snippet
terraform plan my_resource
Use code with caution. Learn more
The terraform plan command will output a plan that shows you what changes will be made. You can then decide whether or not to proceed with the terraform destroy command.

Method 4: Use the terraform force command

If you are sure that you want to delete the resource, you can use the terraform force command. The terraform force command will force Terraform to delete the resource, even if there are changes that have been made to the resource in your infrastructure.

For example, to delete the resource named my_resource even if there are changes that have been made to the resource in your infrastructure, you would run the following command:

Code snippet
terraform force destroy my_resource
Use code with caution. Learn more
The terraform force command is a powerful tool, but it should be used with caution. If you are not sure what you are doing, you should not use the terraform force command.

Method 5: Use the terraform state rm command

If you only want to delete the resource from the Terraform state file, but not from your infrastructure, you can use the terraform state rm command. The terraform state rm command takes the name of the resource as an argument. For example, to delete the resource named my_resource from the Terraform state file, you would run the following command:

Code snippet
terraform state rm my_resource
Use code with caution. Learn more
Once you have deleted the resource from the Terraform state file, you can run the terraform plan command to see what changes will be made if you delete the resource from your infrastructure. If you are satisfied with the changes, you can run the terraform apply command to delete the resource from your infrastructure.

Method 6: Use the terraform refresh command

If you have made changes to the Terraform configuration file, but you have not yet run the terraform apply command, you can use the terraform refresh command to update the Terraform state file. The terraform refresh command will read the Terraform configuration file and update the Terraform state file with the latest information. This will allow you to delete resources that have been removed from the Terraform configuration file.

For example, if you have removed the resource named my_resource from the Terraform configuration file, you can run the following command to update the Terraform state file:

Code snippet
terraform refresh
Use code with caution. Learn more
Once you have updated the Terraform state file, you can run the terraform plan command to see what changes will be made if you delete the resource from your infrastructure. If you are satisfied with the changes, you can run the terraform apply command to delete the resource from your infrastructure.




8. What is a Terraform backend and how might you configure one?

 Terraform backend is a storage location for Terraform state files. The state file stores information about the resources that Terraform has created or modified. This information includes the resource type, the resource name, and the resource configuration. The state file is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

Terraform supports a variety of backends, including:

Local: The local backend stores the state file in a local file. This is the default backend.
S3: The S3 backend stores the state file in Amazon S3.
Azure: The Azure backend stores the state file in Microsoft Azure Blob Storage.
Google Cloud Storage: The Google Cloud Storage backend stores the state file in Google Cloud Storage.
Consul: The Consul backend stores the state file in HashiCorp Consul.
etcd: The etcd backend stores the state file in etcd.
To configure a Terraform backend, you need to specify the backend type and the backend configuration. The backend configuration varies depending on the backend type. For example, the S3 backend configuration includes the S3 bucket name and the S3 access key ID and secret access key.

Once you have configured a Terraform backend, you can use the terraform init command to initialize the backend. The terraform init command will create the state file and store it in the backend.

You can also use the terraform state command to manage the state file. The terraform state command can be used to read, write, and delete the state file.

It is important to note that Terraform will not be able to create or modify resources if the state file is not present. Therefore, it is important to configure a Terraform backend and initialize the backend before you start using Terraform.


9. Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?

View other drafts

















There are a few different ways that Terraform can obtain the credentials it needs for authenticating to an endpoint.

Environment variables: Terraform can read credentials from environment variables. To do this, you need to set the environment variables with the appropriate values. For example, to set the AWS access key ID and secret access key environment variables, you would run the following commands:
Code snippet
export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMIK7MDENG/bPxRfiCYEXAMPLEKEY
Use code with caution. Learn more
Terraform configuration file: Terraform can also read credentials from the Terraform configuration file. To do this, you need to add the credentials to the credentials block in the configuration file. For example, to add the AWS access key ID and secret access key to the configuration file, you would add the following block to the configuration file:
Code snippet
credentials {
  aws {
    access_key_id = "AKIAIOSFODNN7EXAMPLE"
    secret_access_key = "wJalrXUtnFEMIK7MDENG/bPxRfiCYEXAMPLEKEY"
  }
}
Use code with caution. Learn more
Terraform CLI flags: Terraform can also read credentials from the Terraform CLI flags. To do this, you need to specify the credentials with the appropriate flags. For example, to specify the AWS access key ID and secret access key CLI flags, you would run the following command:
terraform apply --access-key-id=AKIAIOSFODNN7EXAMPLE --secret-access-key=wJalrXUtnFEMIK7MDENG/bPxRfiCYEXAMPLEKEY

Terraform provider configuration: Terraform can also read credentials from the Terraform provider configuration. To do this, you need to add the credentials to the provider block in the configuration file. For example, to add the AWS access key ID and secret access key to the configuration file, you would add the following block to the configuration file:
Code snippet
provider "aws" {
  access_key_id = "AKIAIOSFODNN7EXAMPLE"
  secret_access_key = "wJalrXUtnFEMIK7MDENG/bPxRfiCYEXAMPLEKEY"
}
Use code with caution. Learn more
Terraform Cloud: If you are using Terraform Cloud, you can also store your credentials in Terraform Cloud. To do this, you need to create a new credential in Terraform Cloud and then specify the credential ID with the -var-file flag when you run the terraform apply command.
Once you have configured Terraform to obtain the credentials it needs, you can use Terraform to create and manage resources in the cloud.



10. Your terraform code uses public external modules. What do you need to do to ensure that these external modules dependencies 
are resolved before you provision your resources?

here are a few things you can do to ensure that external modules dependencies are resolved before you provision your resources:

Use the terraform init command. The terraform init command will download the external modules and resolve their dependencies.
Use the terraform plan command. The terraform plan command will show you a list of all the resources that will be created or modified, as well as the dependencies of each resource. This will help you to identify any dependencies that have not been resolved.
Use the terraform validate command. The terraform validate command will check your Terraform configuration file for errors. This will help you to identify any errors that could prevent the external modules from being resolved.
Once you have ensured that all of the external modules dependencies are resolved, you can safely run the terraform apply command to provision your resources

11. You have provisioned some infrastructure in the AWS cloud using Terraform. How could you check by querying the state what 
resources you have created using Terraform?


Sure, there are a few ways to check what resources you have created using Terraform.

Using the terraform state list command: The terraform state list command will list all of the resources that have been created or modified by Terraform. This command will show you the resource type, the resource name, and the resource configuration.

Using the terraform state show command: The terraform state show command will show you the configuration of a specific resource. This command is useful if you want to see the details of a specific resource.

Using the terraform state dump command: The terraform state dump command will dump the state file to a file. This file can be opened in a text editor to see the details of all of the resources that have been created or modified by Terraform.

Once you have identified the resources that you have created using Terraform, you can use the terraform destroy command to delete them.

12. What is the recommended approach for editing the Terraform state?


Terraform state is a file that stores information about the resources that Terraform has created or modified. This information includes the resource type, the resource name, and the resource configuration. The state file is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

It is not recommended to edit the Terraform state file directly. If you make changes to the state file directly, Terraform may not be able to track the changes and your infrastructure may not be in the desired state.

The recommended approach for editing the Terraform state is to use the terraform state command. The terraform state command can be used to read, write, and delete the state file.

For example, to add a new resource to the state file, you would use the following command:

Code snippet
terraform state import <resource-id>
Use code with caution. Learn more
To delete a resource from the state file, you would use the following command:

Code snippet
terraform state rm <resource-id>
Use code with caution. Learn more
To update the configuration of a resource in the state file, you would use the following command:

Code snippet
terraform state mv <old-resource-id> <new-resource-id>
Use code with caution. Learn more
It is important to note that if you make changes to the Terraform state file directly, you may need to run the terraform init command to initialize the backend and update the state file.

13. Describe as best as possible what the following code does.
```
terraform {
  backend "s3" {
    bucket   = "techoutcomes-terraforms.tfstate"
    key      = "simplegithubactions"
    region   = "eu-west-1"
  }
}
```

ans

The code you provided is a Terraform backend configuration. It tells Terraform to store its state file in an S3 bucket. The bucket name is techoutcomes-terraforms.tfstate, the key is simplegithubactions, and the region is eu-west-1.

The state file is a file that stores information about the resources that Terraform has created or modified. This information includes the resource type, the resource name, and the resource configuration. The state file is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

By storing the state file in an S3 bucket, Terraform can access the state file from anywhere. This is useful if you are working on a team and you need to share the state file with other team members.

Here are some additional benefits of storing the state file in an S3 bucket:

Scalability: S3 buckets can scale to meet the needs of your infrastructure.
Reliability: S3 buckets are highly reliable and are backed by Amazon's global infrastructure.
Security: S3 buckets can be secured with a variety of mechanisms, including encryption and access control.
If you are using Terraform to manage your infrastructure, I recommend storing the state file in an S3 bucket. This will give you the flexibility, scalability, reliability, and security that you need to manage your infrastructure effectively.


14. Describe as best as possible what the following code does.
```
provider "aws" {
  region = local.region
}
```

The code you provided is a Terraform provider configuration. It tells Terraform to use the AWS provider and to set the region to the value of the local.region variable.

The provider block is used to configure the providers that Terraform will use to create and manage resources. The aws provider is used to create and manage resources in the AWS cloud.

The region attribute is used to specify the region that Terraform will use to create and manage resources. The region is a geographic location where AWS resources are located.

The local.region variable is a Terraform local variable. Local variables are variables that are defined in the Terraform configuration file. The region variable is used to store the region that Terraform will use to create and manage resources.

By using the local.region variable, you can make the region configuration more flexible. This is because you can change the region value in the Terraform configuration file without having to change the provider block.


15. What does is mean to lock and Terraform state file and why is it important to implement a locking mechanism for the state file?

When you create or update infrastructure using Terraform, it stores information about the resources it has created or modified in a state file. This state file is used to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

Locking the Terraform state file prevents multiple Terraform processes from accessing the state file at the same time. This prevents conflicts between the different processes and ensures that the state file is always consistent.

It is important to implement a locking mechanism for the state file because it helps to prevent conflicts and ensure that the state file is always consistent. Without a locking mechanism, it is possible for two Terraform processes to try to access the state file at the same time. This can lead to conflicts, such as two processes trying to create the same resource.

There are a few different ways to implement a locking mechanism for the Terraform state file. The most common way is to use the terraform state lock command. This command will lock the state file for a specified amount of time. Once the lock expires, the state file will be unlocked and other Terraform processes will be able to access it.

Another way to implement a locking mechanism for the Terraform state file is to use a third-party tool, such as consul or etcd. These tools provide a distributed locking mechanism that can be used to lock the state file across multiple machines.

If you are using Terraform to manage your infrastructure, I recommend implementing a locking mechanism for the state file. This will help to prevent conflicts and ensure that the state file is always consistent.


16. Describe in details what each of the following Terraform command does;
a) terraform init
b) terraform apply --auto-approve
c) terraform fmt
d) terraform validate
e) terraform destroy

a) terraform init

The terraform init command initializes a Terraform working directory. This command downloads the necessary providers and modules, and creates the state file.

b) terraform apply --auto-approve

The terraform apply --auto-approve command applies the Terraform configuration to the target infrastructure. This command creates or updates resources, and updates the state file.

c) terraform fmt

The terraform fmt command formats the Terraform configuration file. This command makes the configuration file easier to read and understand.

d) terraform validate

The terraform validate command validates the Terraform configuration file. This command checks the configuration file for errors and warnings.

e) terraform destroy

The terraform destroy command destroys the Terraform configuration from the target infrastructure. This command deletes resources, and updates the state file.

Here are some additional details about each command:

a) terraform init

The terraform init command initializes a Terraform working directory by downloading the necessary providers and modules, and creating the state file. The state file stores information about the resources that Terraform has created or modified. This information is used by Terraform to track changes to your infrastructure and to ensure that your infrastructure is always in the desired state.

b) terraform apply --auto-approve

The terraform apply --auto-approve command applies the Terraform configuration to the target infrastructure. This command creates or updates resources, and updates the state file. The --auto-approve flag tells Terraform to automatically approve all changes. This is useful for automating deployments.

c) terraform fmt

The terraform fmt command formats the Terraform configuration file. This command makes the configuration file easier to read and understand. Terraform configuration files can become complex, and the terraform fmt command can help to make them more readable.

d) terraform validate

The terraform validate command validates the Terraform configuration file. This command checks the configuration file for errors and warnings. Terraform configuration files can contain errors, such as typos or syntax errors. The terraform validate command can help to identify these errors before you try to apply the configuration to your infrastructure.

e) terraform destroy

The terraform destroy command destroys the Terraform configuration from the target infrastructure. This command deletes resources, and updates the state file. The terraform destroy command can be used to clean up resources that you no longer need.


17. How would you name a file so that it is recognised by Terraform when you run terraform plan or apply?


Terraform recognizes files that have a .tf extension. So, if you want Terraform to recognize a file, you need to name it with a .tf extension. For example, if you have a file called main.tf, Terraform will recognize it when you run terraform plan or terraform apply.

You can also use the -f flag to specify a file to Terraform. For example, if you have a file called other.tf, you can run terraform plan -f other.tf to have Terraform recognize that file.


18. What is the purpose of the Terraform plan command and why is it important to read carefully the output of the plan?


1
The Terraform plan command creates an execution plan, which lets you preview the changes that Terraform plans to make to your infrastructure. The output of the plan command shows you what resources Terraform will create, update, or delete. It also shows you the configuration of the resources that Terraform will create.

It is important to read carefully the output of the plan command before you run the apply command. This will help you to understand what changes Terraform will make to your infrastructure. If you do not understand the output of the plan command, you may accidentally make changes to your infrastructure that you did not intend to make.

Here are some of the benefits of reading the output of the plan command:

Prevents accidental changes: By reading the output of the plan command, you can prevent accidental changes to your infrastructure. If you see a change that you do not understand, you can investigate it before you run the apply command.
Identifies potential problems: The output of the plan command can identify potential problems with your infrastructure. For example, if Terraform plans to create a resource that already exists, the output of the plan command will show you this.
Provides a record of changes: The output of the plan command provides a record of the changes that Terraform has made to your infrastructure. This can be useful for troubleshooting problems or for auditing your infrastructure.


19. What Terraform concept would you use to ensure your code is re-useable?


There are a few Terraform concepts that you can use to ensure your code is reusable.

Modules: Modules are a way to organize your Terraform code into reusable units. Modules can be used to create common infrastructure components, such as web servers, databases, and load balancers.
Variables: Variables are a way to pass values into your Terraform code. Variables can be used to make your code more flexible and to avoid hard-coding values.
Outputs: Outputs are a way to get values from your Terraform code. Outputs can be used to pass values out of your Terraform code and into other systems.
By using modules, variables, and outputs, you can make your Terraform code more reusable and easier to maintain.


20. Terraform provisioning are directory-oriented in the sense that the resources created in a "Terraform apply" are defined in the same directory and each directory maps to a state. You want to created three different environment (dev, test and production) from one directory containing the main Terraform definitions. How would you organise your file and directory system?


Here is one way to organize your file and directory system for multiple environments:

Code snippet
├── main.tf
├── variables.tf
└── environments
    ├── dev
    │   ├── main.tf
    │   └── variables.tf
    └── test
        ├── main.tf
        └── variables.tf
    └── production
        ├── main.tf
        └── variables.tf
Use code with caution. Learn more
The main.tf file contains the main Terraform configuration. The variables.tf file contains the variables that are used by the Terraform configuration. The environments directory contains the Terraform configurations for each environment. Each environment directory contains its own main.tf and variables.tf files.

When you run terraform apply, Terraform will apply the configuration in the current directory. If you are in the dev directory, Terraform will apply the dev configuration. If you are in the test directory, Terraform will apply the test configuration. And if you are in the production directory, Terraform will apply the production configuration.

This approach has a few advantages:

It is easy to manage multiple environments.
It is easy to share code between environments.
It is easy to test changes in a development environment before promoting them to a production environment.


21. What do you understand by Terraform partial backend configuration?
22. What do you understand by the <b> Chicken-and-Egg </b> problem with respect to Terraform backend configuration and how is it generally solved.

Terraform partial backend configuration

A partial backend configuration is a Terraform configuration that does not specify all of the required backend configuration arguments. This can be useful if you want to share the same Terraform configuration between multiple environments, but you want to use different backend configurations for each environment.

For example, you might have a Terraform configuration that creates a web server in AWS. You might want to share this configuration between your development, staging, and production environments. However, you might want to use different S3 buckets for storing the Terraform state file in each environment.

In this case, you could use a partial backend configuration. In the backend.tf file, you would specify the backend type and the required arguments for the backend type. You would then specify the environment-specific arguments in the variables.tf file.

For example, the following backend.tf file specifies a remote backend with the s3 backend type:

Code snippet
terraform {
  backend "remote" {
    hostname = "app.terraform.io"
    organization = "my-company"
  }
}
Use code with caution. Learn more
The following variables.tf file specifies the environment-specific arguments:

Code snippet
variable "environment" {
  type = string
}

variable "s3_bucket" {
  type = string
}
Use code with caution. Learn more
When you run terraform init, Terraform will use the backend.tf file to initialize the backend. Then, Terraform will use the variables.tf file to set the environment-specific arguments.

Chicken-and-Egg problem

The chicken-and-egg problem with respect to Terraform backend configuration is the problem of how to initialize the backend when the backend configuration is stored in the state file.

For example, you might have a Terraform configuration that creates a database in AWS. You might want to use the s3 backend to store the Terraform state file. However, the s3 backend requires the S3 bucket name as a configuration argument. And the S3 bucket name is stored in the Terraform state file.

In this case, you cannot initialize the backend without the S3 bucket name. And you cannot get the S3 bucket name without initializing the backend.

There are a few ways to solve the chicken-and-egg problem:

Use a local backend: A local backend stores the state file in a local file system. This is the simplest way to solve the chicken-and-egg problem.
Use a remote backend with a dynamic configuration: A remote backend with a dynamic configuration allows you to specify the backend configuration arguments as environment variables. This can be used to solve the chicken-and-egg problem by passing the S3 bucket name as an environment variable when you run terraform init.
Use a Terraform Cloud workspace: Terraform Cloud workspaces allow you to create and manage multiple Terraform configurations in the same workspace. This can be used to solve the chicken-and-egg problem by creating a workspace for each environment and specifying the S3 bucket name in the workspace configuration.


23. You want to use the Terraform public module "[terraform-aws-modules/ec2-instance/aws](https://github.com/terraform-aws-modules/terraform-aws-ec2-instance)" as shown in the code below. Go and look in the public module and fill in some of the interface value you will need in order to create the module
```
module "ec2_instance" {
  source = "terraform-aws-modules/ec2-instance/aws"

}
```


mi_id: The AMI ID of the instance you want to create.
instance_type: The instance type of the instance you want to create.
key_name: The name of the SSH key you want to use to connect to the instance.
vpc_id: The ID of the VPC you want to create the instance in.
subnet_id: The ID of the subnet you want to create the instance in.
security_groups: A list of security groups you want to associate with the instance.
tags: A map of tags you want to associate with the instance.
For example, the following code would create an instance with the AMI ID ami-0123456789abcdef0, the instance type t2.micro, the SSH key my-key-pair, the VPC ID vpc-1234567890abcdef, the subnet ID subnet-1234567890abcdef, the security group ID sg-1234567890abcdef, and the tags Name=MyInstance and Environment=Production:

Code snippet
module "ec2_instance" {
  source = "terraform-aws-modules/ec2-instance/aws"

  ami_id = "ami-0123456789abcdef0"
  instance_type = "t2.micro"
  key_name = "my-key-pair"
  vpc_id = "vpc-1234567890abcdef"
  subnet_id = "subnet-1234567890abcdef"
  security_groups = ["sg-1234567890abcdef"]
  tags = {
    Name = "MyInstance"
    Environment = "Production"
  }
}



## System Architecture and Application Design, Cloud Computing (AWS)

1. You have an application running on one server in the cloud serving requests from customers. There is a sudden increase in request from customers reaching the application and a lot of requests are failing or are extremely slow.
* Draw a diagram showing this architecture.
* How could you re-architect the application to allow it to handle more request?
* Draw a diagram of the new design.

2. You wish to SSH from you local laptop to your server in the AWS cloud. Describe the configuration you will need in place on your local laptop and on the AWS cloud to enable this.

3. What role does a database play in the overall business system design and what steps might you take to ensure the database is resilient and highly available?

4. Describe as best as possible what a three-tier architecture is? Which of the three tier would you deploy so that it is accessible to the internet?


ANswer 1-4

Original architecture
The original architecture is a single-tier architecture, where the application is running on a single server. This architecture is not scalable, and it can't handle a sudden increase in requests.

single-tier architectureOpens in a new windowBitnami Documentation
single-tier architecture
New architecture

The new architecture is a three-tier architecture, where the application is divided into three tiers: the presentation tier, the application tier, and the data tier. This architecture is more scalable, and it can handle a sudden increase in requests.

three-tier architectureOpens in a new windowTechTarget
three-tier architecture
The presentation tier is responsible for displaying the application's user interface. The application tier is responsible for processing the user's requests and returning the results. The data tier is responsible for storing the application's data.

To re-architect the application to allow it to handle more requests, we can add more servers to each tier. For example, we can add more web servers to the presentation tier, more application servers to the application tier, and more database servers to the data tier.

Configuration required to SSH from local laptop to AWS cloud server
On the local laptop, we need to install the SSH client software. We also need to know the public IP address of the AWS cloud server.

On the AWS cloud server, we need to open the SSH port. We can do this by editing the security-groups.json file and adding a rule that allows TCP traffic on port 22.

Once we have made these changes, we can SSH from the local laptop to the AWS cloud server by running the following command:

Code snippet
ssh -i <key-file> <user>@<public-ip-address>
Use code with caution. Learn more
where <key-file> is the path to the SSH key file, <user> is the username of the account on the AWS cloud server, and <public-ip-address> is the public IP address of the AWS cloud server.

Role of a database in the overall business system design
The database plays a critical role in the overall business system design. It stores the data that is used by the application. The database must be designed to meet the needs of the application. For example, if the application needs to store a large amount of data, the database must be designed to be scalable.

To ensure that the database is resilient and highly available, we can use a database cluster. A database cluster is a group of database servers that work together to provide a single database service. If one database server in the cluster fails, the other database servers in the cluster can continue to provide service.

Three-tier architecture
A three-tier architecture is a software architecture that divides an application into three logical tiers: the presentation tier, the application tier, and the data tier.

The presentation tier is responsible for displaying the application's user interface. The application tier is responsible for processing the user's requests and returning the results. The data tier is responsible for storing the application's data.

The three tiers are connected by a network. The presentation tier communicates with the application tier using a web service. The application tier communicates with the data tier using a database.

The three-tier architecture is a scalable and flexible architecture. It can be used to build a wide variety of applications.

The tier that would be deployed so that it is accessible to the internet is the presentation tier. The presentation tier is responsible for displaying the application's user interface. This is the tier that users interact with, so it must be accessible to the internet.

5. Create a server (EC2 instance - Amazon Linux 2023, Free tier) in your AWS account and do the following.
* Log onto the EC2 instance from your local machine.
* Copy a file from your local machine onto the EC2 instance.
* What would you have to do to allow someone else to log onto your server?
* Add this public key into your authorised_key file
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCkyNUp8esDy/6wOaBVo7Xq1JVuhuF3E8kQPWRAAdLPdbhwwpH2+SPuFoBF4Pk4RWkpNQMBZp+9uo9NNXB8PpHQxF5vFUrhJG8cmymdWdRG4YpXBOhThwU6TFo/qdz7E3oVYMkWAeuXgVpMRhwpHmy+Rv+JBx8g9Nc7UFMiMz1mHqYq7qCOaLGKBMWaw33Z3PUzZlNQk9MzM5wNaIOXg5QSEXaNNpQt0vyYbS5guVSLiN92UEypZqEwsqW2E1yUySjCkbCgO6kWVlYONUZqS9dVzi4QZ/DzwZWZz8hdYg8u1M+b3twmLlNHzZn9qkL5sP9c9SVj5eLFAarYgtAfg05t sunatrakey
```
* Shut down your server (do not terminate it). We shall be performing some tests on the machine later.

 1012  ls -la
 1013  cd .ssh
 1014  ls -ltr
 1015  chmod 600 devteaops.pem
 1016  vim devteaops.pem
 1017  vim devteaops.pem
 1018  ssh -i devteaops.pem  ec2-user@3.86.245.136
 1019  history
devteaops@Aderinlola:~/.ssh$


6. What is a bastion server and why is it required in some network architectures?
7. In terms of accessibility, what is the difference between a Public IP and a Private IP
8. Describe at a high level how the ssh system works.
9. When you create a key pair on AWS, describe where the keys are stored.
10. When you create an EC2 instance on AWS, a network interface is also created and a Private IP is attached with the interface. Describe why this is important.


ans 6-10


6. A bastion server is a server that is exposed to the public internet and is used to manage other servers that are not exposed to the public internet. Bastion servers are often used in network architectures where there are a large number of servers that need to be managed, but only a few servers need to be accessible to the public internet.
Bastion servers are required in some network architectures because they provide a secure way to manage servers that are not exposed to the public internet. By using a bastion server, administrators can connect to the bastion server using a secure protocol, such as SSH, and then use the bastion server to connect to the other servers. This helps to protect the other servers from attack.

7. In terms of accessibility, the main difference between a public IP and a private IP is that a public IP is accessible from the public internet, while a private IP is not. This means that a server with a public IP can be accessed by anyone on the internet, while a server with a private IP can only be accessed by other servers on the same network.
Public IPs are typically used for servers that need to be accessible from the public internet, such as web servers and mail servers. Private IPs are typically used for servers that do not need to be accessible from the public internet, such as database servers and application servers.

8. SSH, or Secure Shell, is a network protocol that allows users to securely access a remote computer. SSH uses encryption to protect the data that is transmitted between the user's computer and the remote computer. This makes SSH a very secure way to access remote computers.
To use SSH, the user must first create a key pair. A key pair consists of a public key and a private key. The public key is stored on the remote computer, and the private key is stored on the user's computer.

When the user connects to the remote computer using SSH, the user's computer sends the remote computer its public key. The remote computer then uses the public key to encrypt the data that is transmitted between the two computers. The encrypted data is then sent to the user's computer, where it is decrypted using the user's private key.

9. When you create a key pair on AWS, the keys are stored in your AWS account. You can access the keys from the AWS Management Console or the AWS Command-Line Interface.

10. When you create an EC2 instance on AWS, a network interface is also created and a Private IP is attached with the interface. This is important because it allows the EC2 instance to communicate with other servers on the same network.

The Private IP is not accessible from the public internet, which helps to protect the EC2 instance from attack.



## Site Reliability Engineering (SRE), Troubleshooting, Observability

1.

2.

3.

4.

5.



## DevOps and Agile Transformation principles and methodology

1.

2.

3.

4.

5.


## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |
| :---        |    :----:   | :---  |
| 1  | ls             |List the contents of a directory  |
| 2  | cd             | Change directory                 |
| 3  | pwd            |   Print the working directory    |
| 4  | mkdir          |  Create a directory              |
| 5  | rmdir          | Remove a directory               |
| 6  | touch          |  Create a file                   |
| 7  | cat            | Display the contents of a file   |
| 8  | grep           | Search for a pattern in a file   |
| 9  | sort           | Sort the lines in a file         |
|10  | uniq           |Remove duplicate lines from a file|

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | ssh            | network protocol that allows users to securely access a remote computer   |
| 2  | chmod          |allows users to change the permissions of files and directories            |
| 3  | pwd            | prints the current working directory                                      |
| 4  | vim            | text editor                                                               |
| 5  | history        |built-in shell tool that displays a list of commands used in the terminal session   |
| 6  |-U, --unsorted  |do not sort; list entries in directory order                               |
| 7  |-v, --version   |show ls version information and exit                                       |    
| 8  |-x, --one-per-line|           list entries one per line                                     |
| 9  |-1, --one-line  |            list entries one per line                                      |
|1 0 | cp             |  copy files and directories                                               |

