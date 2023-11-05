# DevSecOps

### Introduction

DevSecOps is a common framework which describes the mechanisms which developers use to develop, secure and deploy their code. This is particularly popular within the cloud space as it allows developers to work at pace, whilst allowing information security teams to assure the pipeline tasks to automatically catch poor code quality and vulnerabilities such as credentials in repositories.

Tools in this space are *constantly* changing, so please don't take this as an exhaustive list. If you have experience of working with a specific tool, [submit a feature request](https://github.com/ascoarchitect/multi-cloud-architecture/issues/new) with all the details to get them added here for all to learn.

### Recommended Tools

Most of the tools below use the declarative languages YAML or JSON, so it's recommended to become familiar with how to structure these languages to make it easier to understand the required structure and diagnose issues with deployments.

JSON: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON<br/>
YAML: https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html

|Tool|Purpose|Key Highlights|More Details|
|---|---|---|---|
|Ansible<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-Agnostic-darkgreen)|Provisioning, configuration management and application deployment|Ansible is a tool which is used widely in the cloud development space for managing the configuration of instances, and deploying software on build. Take a look through [Ansible Galaxy](https://galaxy.ansible.com) for the wide selection of code snippets (playbooks) which are vendor and community authored. Examples of where Ansible could be used would be domain joining machines on build or configuring packages which are installed on instance start-up. This tool has specific benefits over the user-data approach as it doesn't just run once.|https://www.ansible.com|
|Terraform<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-Agnostic-darkgreen)|Infrastructure as Code (IaC)|HashiCorp Terraform is an infrastructure as code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share. You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage low-level components like compute, storage, and networking resources, as well as high-level components like DNS entries and SaaS features. Hashicorp has a robust [registry](https://registry.terraform.io) of modules and provider which vendor and community authored which can be used to accelerate IaC development and use best-practice configurations.|https://www.terraform.io|
|AWS CloudFormation<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-AWS-orange)|Infrastructure as Code (IaC)|An AWS-specific service which allows developers to deploy resource stacks on to AWS. CloudFormation is written in JSON or YAML format and can be used to develop blueprints of repeatable code which can be deployed from the AWS Console or a CI/CD pipeline. You would consider using CloudFormation if the intention is to only deploy to AWS and not use automation for other clouds or technologies. If you are considering multi-cloud or services which need to be managed aside from the AWS resources, then consider using Terraform instead.|https://aws.amazon.com/cloudformation|
|Cloud Deployment Manager<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-Google%20Cloud-blue)|Infrastructure as Code (IaC)|Google Cloud Deployment Manager is an infrastructure deployment service that automates the creation and management of Google Cloud resources. Write flexible template and configuration files and use them to create deployments that have a variety of Google Cloud services, such as Cloud Storage, Compute Engine, and Cloud SQL, configured to work together. CDM uses YAML format for the infrastructure code.|https://cloud.google.com/deployment-manager/docs|
|Bicep<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-Azure-lightblue)|Infrastructure as Code (IaC)|Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources. In a Bicep file, you define the infrastructure you want to deploy to Azure, and then use that file throughout the development lifecycle to repeatedly deploy your infrastructure. Like AWS CloudFormation and Google Cloud Deployment Manager, Bicep is an Azure-specific deployment language for infrastructure code.|https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview|
|Packer<br/>![Static Badge](https://img.shields.io/badge/Cloud%20Provider-Agnostic-darkgreen)|Images as Code|HashiCorp Packer is a community tool that enables you to create identical machine images for multiple platforms from a single source template. The most common use case is creating golden images that teams across an organisation can use in cloud infrastructure. Packer uses the same development language as Terraform (HCL) so if you're already using Terraform for your IaC capability, then these tools can be closely integrated|https://www.packer.io/|

### Terraform

I'm going to include an extra section on Terraform here, because I can't emphasis enough the need to become familiar with its approach and application. I doubt many if any cloud engineer or cloud developer will not come across Terraform at some point, so here's a basic breakdown of some of the elements.

There are three elements to developing Terraform, including writing the configuration files, planning your deployment then applying your code.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/devsecops/terraform-approach.png" alt="Terraform Approach" style="height: 400px;"/>

The plan phase allows you to see the changes that your code will make to an environment before it is applied, therefore you can quickly spot any issues before they become irreversible. When it comes to 'applying' your changes using terraform apply, I have come across developers who skip the plan phase and just run ```terraform apply -auto-approve``` which just deploys the code without any checks or warning. Now, whilst there are cases where -auto-approve is used, such as in a pipeline task for automated deployment, these are always preceded with a plan phase where validation can be carried out. We're all human and prone to mistakes - see it as an advantage rather than an annoying delay.

Finally, I want to cover state. Terraform uses a state file which is essentially a definitive record of what it believes is the current 'state' of the deployment. When you run a plan, terraform will read the state file then compare the changes with the existing environment. As this is just a static file, it's highly recommended that this is places in a fault-tolerant and secure location due to its importance and plain-text sensitivity. Each provider has recommendations on how to store your state file, an example of which is on AWS where it's stored on S3 and uses Amazon DynamoDB as a locking table.

Where you have infrastructure which has been manually deployed using the console and you now want this to be managed using Terraform, you can also import resources into your state file using the ```terraform import``` function.

Read more about all these capabilities and configurations here: https://developer.hashicorp.com/terraform/cli

### Power of the Pipeline

Hopefully after reading this section, you'll get a feel for why I chose to give it this title. The development pipeline is what stands between the code that a developer writes and the product that the code goes on to create. It is there to hold everyone to account, and act as an authoritative intermediary which prevents any one 'actor' or human from making all the changes. The benefit this provides is that it uses automation to carry out many of the tasks that would require peer review or security auditing, and instead allows those same personas to secure the checks instead.

Think about this as an example: The Information Security team are concerned about the risk of a developer accidentally (or unfortunately in rare cases, intentionally) committing credentials into a repository which is then published into the application or public resource. Of course, the risk is that a hacker could obtain these credentials and either launch an attack on the platform or sell the credentials to a number of rather unsavoury actors. Taking the human validation approach would mean that all code would need to be checked manually for credentails and signed off by the information security team. The obvious problem here is that this then promotes that team to a bottleneck which will ultimately lead to reduced throughput (or increased cycle time) for each release.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/devsecops/credential-scan.png" alt="Credential Scanning" style="height: 300px;"/>

Introducing the pipeline. Rather than manually checking code, you create a CI task which automatically scans all the code for known 'patterns' and rejects a code commit if it finds anything that matches. The information security team can still monitor the tool and even carry out spot checks, but what this now means is that a developer can work much faster, and safe in the knowledge that their code and human errors are being checked over by one of a series of pipeline checks.

### Continuous Integration (CI)

Continuous Integration is the first part of the pipeline and it focuses on the building and testing of an application. The tasks are usually started off with a developer committing their code to a repository which automatically starts the build process. Now, the tasks that make up a build can vary based on the type of application being writted, but you would expect to have a compiler configured with the build tasks required, or in the case of IaC, it would run a plan task to project all the changes that will be made to the infrastructure. You can expect to see tools such as Jenkins, Packer, Terraform, Docker and many others used for this stage.

Now the code is build or the deployment planned, next the testing takes place. These tests will carry out a variety of different functions, and would usually be defined as a collaborative effort between the developers, the testers, the infrastructure and security teams. Here is a non-exhaustive list of the tests you would expect to be carried out depending on what is being deployed:

* Unit Testing - Pre-defined tests carried out on chunks of code to verify it functions as expected
* Static Analysis (SAST) - Checking code quality and whether any vulnerabilities have been introduced in how the code has been developed. This could be where Terraform code is not aligning with best practice such as having a security group which is too permissive. Technically it would work, but it's poor practice, and that is where a SAST check would fail the test.
* Functional Analysis - This is for verifying that the application as a whole is functioning as required. You would expect to see a tool such as Selenium used here which carrys out a set of steps to ensure that the appplication doesn't respond incorrectly. An example here would be logging in to a web application - Selenium would launch a browser session in a contained environment, navigate to the right page, enter test credentials into the web page and automate the clicking of the login button.
* Vulnerability Analysis - Used for ensuring that the code is secure and doesn't introduce any unintentional vulnerabilities such as back doors or session hijacking opportunities which could be attacked.
* Dependency Analysis - When using external packages which are written by third parties, it's important to validate that those packages are not introducing issues into your application, so this analysis looks at any modules or packages which are being imported as part of the build process.
* Performance Testing and Profiling - Finally, this stage would look at how performant your application is and map out, or profile, each step so a developer can understand whether there's an inefficient SQL query causing slow load times, or any assets which haven't been optimised for size and resolution.

### Continuous Delivery (CD)

Congratulations, your code has passed all the required checks so it's now time to deploy. Release automation takes care of connecting to the deployment servers or cloud environments and executing the deployment of the changes which have been committed into the repository. The advantage this has is that it can automate the injection of variables and secrets to connect and configure, often using just-in-time credentials to prevent the use of long-lived secrets which could be exposed. Additionally, you can configure your deployment steps to deploy to multiple environments (dev, test, staging, production etc.) using the same mechanism. This can be seen where code is 'promoted' up through environments for different teams to use and test.

### Pre-Commit: "A framework for managing and maintaining multi-language pre-commit hooks."

As the name describes, the pre-commit framework encompases a series of tests which can be run before code it committed to a repository. As you learned earlier when looking at CI and CD, the pipeline runs all the required tests for the application, however, these can often take some time to execute and fail which leaves the developer constantly waiting for results to be posted back to them so they know whether the code works. Pre-commit hooks can be fired localled which essentially gives a developer instant feedback for certain tests which is great for them, but you can also block code from being committed under certain circumstances.

Pre-commit is configured using a static YAML file which defines the tests which are carried out, and also which ones must pass to allow the commit to take place. The developer installs the pre-commit hooks which installs all the required test packages on their machine, allowing tests to run in that environment. The framework supports a number of different languages, and in some cases can automatically remediate findings for the developer.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/devsecops/pre-commit.png" alt="Credential Scanning" style="height: 300px;"/>

You can find out more about pre-commit and how you might benefit from introducing it into your workflow [here](https://pre-commit.com/).

### Training and Development

Draft

### Further Reading

**[Infrastructure as Code for Beginners: Deploy and Manage your cloud-based services with Terraform and Ansible](https://amzn.to/40pKAsK)**

A great introduction into how Terraform and Ansible can be used in a cloud development environment.

**[What is Continuous Integration?](https://about.gitlab.com/topics/ci-cd/benefits-continuous-integration/)**

The team at GitLab have written a blog post which expands on what CI is all about.

**[What is GitOps?](https://about.gitlab.com/topics/gitops/)**

You might come across the term GitOps when describing ways of working with DevOps. GitOps is essentially a framework which was originally coined by Alexis Richardson, CEO, Weaveworks, and encompases "scalable applications in modern, dynamic environments such as public, private, and hybrid cloud". You can read more about what it means and how it might be a way of working you could look to adopt.
