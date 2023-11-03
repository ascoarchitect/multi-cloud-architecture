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
|Ansible|Provisioning, configuration management and application deployment|Ansible is a tool which is used widely in the cloud development space for managing the configuration of instances, and deploying software on build. Take a look through [Ansible Galaxy](https://galaxy.ansible.com) for the wide selection of code snippets (playbooks) which are vendor and community authored. Examples of where Ansible could be used would be domain joining machines on build or configuring packages which are installed on instance start-up. This tool has specific benefits over the user-data approach as it doesn't just run once.|https://www.ansible.com|
|Terraform|Infrastructure as Code (IaC)|HashiCorp Terraform is an infrastructure as code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share. You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage low-level components like compute, storage, and networking resources, as well as high-level components like DNS entries and SaaS features. Hashicorp has a robust [registry](https://registry.terraform.io) of modules and provider which vendor and community authored which can be used to accelerate IaC development and use best-practice configurations.|https://www.terraform.io|
|AWS CloudFormation|Infrastructure as Code (IaC)|An AWS-specific service which allows developers to deploy resource stacks on to AWS. CloudFormation is written in JSON or YAML format and can be used to develop blueprints of repeatable code which can be deployed from the AWS Console or a CI/CD pipeline. You would consider using CloudFormation if the intention is to only deploy to AWS and not use automation for other clouds or technologies. If you are considering multi-cloud or services which need to be managed aside from the AWS resources, then consider using Terraform instead.|https://aws.amazon.com/cloudformation|
|Google Cloud Deployment Manager|Infrastructure as Code (IaC)|Google Cloud Deployment Manager is an infrastructure deployment service that automates the creation and management of Google Cloud resources. Write flexible template and configuration files and use them to create deployments that have a variety of Google Cloud services, such as Cloud Storage, Compute Engine, and Cloud SQL, configured to work together. CDM uses YAML format for the infrastructure code.|https://cloud.google.com/deployment-manager/docs|
|Bicep|Infrastructure as Code (IaC)|Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources. In a Bicep file, you define the infrastructure you want to deploy to Azure, and then use that file throughout the development lifecycle to repeatedly deploy your infrastructure. Like AWS CloudFormation and Google Cloud Deployment Manager, Bicep is an Azure-specific deployment language for infrastructure code.|https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview|
|Packer|Images as Code|HashiCorp Packer is a community tool that enables you to create identical machine images for multiple platforms from a single source template. The most common use case is creating golden images that teams across an organisation can use in cloud infrastructure. Packer uses the same development language as Terraform (HCL) so if you're already using Terraform for your IaC capability, then these tools can be closely integrated|https://www.packer.io/|

### Power of the Pipeline

Draft

### Continuous Integration (CI)

Draft

### Continuous Deployment (CD)

Draft

### Pre-Commit

Draft

### Training and Development

Draft

### Further Reading

[Infrastructure as Code for Beginners: Deploy and Manage your cloud-based services with Terraform and Ansible](https://amzn.to/40pKAsK)

A great introduction into how Terraform and Ansible can be used in a cloud development environment.
