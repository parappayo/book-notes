
# About

[Terraform Up & Running: Writing Infrastructure as Code](https://www.terraformupandrunning.com/)
by Yevgeniy Brikman
O'Reilly, March 2017

# Thoughts

Nice, ground-floor overview of Terraform. Lots of accessible examples. Unfortunately, AWS and Terraform are rapidly evolving, so some specifics (eg. Terraform backends) become out-dated quickly. This edition is current to Terraform 0.8.0.

# Take-Aways

* Chef and Ansible offer a procedural style of configuration script which makes their deployments not idempotent; Terraform uses a declarative style
* git ignore `.terraform`, `*.tfstate`, `*.tfstate.backup`
* aws_autoscaling_group has a load_balancers attribute so that each instance can register itself with a load balancer as it starts up rather than the load balancer having a static list of instances
* Port 8080 is used because ports under 1024 require root access to listen on. Load balancers may listen on port 80 and redirect to port 8080.
* tfstate files by default are stored locally; shared via Terrform backend; are private API, editing them manually is discouraged; contain security sensitive data, should definitely not be in your repo.
* Isolation via modules: a Terraform module is just the set of config files in a directory. Tfstate files are created on a per-directory basis, so splitting the config into separate directories per subsystem reduces the blast radius of a corrupted config; consider creating a separate directory per deployment environment (dev, staging, prod).
* Input variables act as inputs to a module, output variables act as outputs; for instance, a module that provisions an ASG could take min and max size as inputs, and return the name of the created ASG and the DNS of its ESG as outputs.
* File paths are relative to the working directory by default, but modules can use ${path.module} to create paths relative to the module dir.
* TF_VAR_foo - naming convention for environment variables to be used by a Terraform config
* Modules should prefer defining resources in separate blocks, rather than inline blocks, to maintain flexibility; otherwise routing rules can conflict due to mixing both styles.
* Terraform provides limited flow control in the form of a count meta-parameter, ternary operator, and lifecycle block (`create_before_destroy`); count setting controls creating copies of a resource, `${count.index}` helps give the copies individual names; `count = 0` can be used to conditionally skip creating a resource
element function automatically wraps using the mod(list length) of the given index.
* Terraform config casts boolean values to 1 or 0, so `count = ${var.my_flag}` allows a boolean setting to toggle a resource
* `count` cannot use dynamic data such a fetched provider attributes or attribute of a resource after it is created; `error: resource count can't reference a resource variable`
* Zero-downtime deployment may reset ASG to its minimum pool count in spite of any configured auto-scaling policies; one work-around is to have ASG policies run every minute to keep the server count current.
* Terraform plan command only looks at tfstate, not the deployed resources, so any conflicts there won't be caught until a terraform apply is attempted; eg. if a resource already exists
* Refactoring Terraform config can be perilous; accidentally re-provisioning an ELB will cause an outage.
* AWS provides an asynchronous API where many provisioning operations respond immediately even if they don't succeed right away; this can cause flaky behaviour in Terraform apply, such that apply needs to run several times to fully complete a plan; latency across regions can make it worse
* The Golden Rule of Terraform: the master branch of the live infrastructure repo should accurately and clearly represent what is currently deployed. Consider having separate repos for Terraform modules and the live infrastructure.
* A code review for Terraform config should include plan output.
* Credentials can be in the provider block or in `~/.aws/credentials`
* AMI IDs are region specific

# Concepts

* `${file(path)}` - interpolation function to read the contents of a file into the script
* `*` - splat operator - used to get a list value from an attribute name, eg. if `aws_iam_user.users.0.arn` is the ARN of a user, then `aws_iam_user.users.*.arn` is a list of user ARNs
* `template_file` - Terraform data block type that can read a script file and substitute given variables on it, useful for keeping embedded bash scripts separate from config
* `terraform console` - REPL prompt to experiment with terraform functions
* `terraform destroy` - will remove all resources created by a terraform config
* `terraform fmt` - format command, applies consistent styling to Terraform config
* `terraform graph` - command that displays depency graph
* `terraform import` - command to create tfstate from existing infrastructure, works on one resource at a time
* `terraform init` - run on a new project or repo clone before using other Terraform commands
* `terraform remote config` - command to init a terraform project from remotely stored state files
* `terraform_remote_state` - read remote read-only state, useful for getting output params from other terraform configurations that were deployed, eg. IP address of a db server that was provisioned
* `user_data` - Terraform param that specifies custom shell script to run
* Ad-hoc Scripts - often shell scripts but could be a combationation of anything, tends not to have robust error handling, tends not to be idempotent, no standards to adhere to
* Agent Software - Chef Client, Salt Minion, Puppet Agent; service software that needs to be installed on deployment target servers before deployments can be run against them, generally requires some outbound ports to be open
* CAMS - Culture, Automation, Measurement, Sharing; the values of DevOps
* CIDR block - Classless Inter-Domain Routing
* Containers - Docker, CoreOS rkt; isolated application environments that share an underlying kernel, allows standardizing configuration without as much overhead as a VM
* Data Source - ${data.type.name.attribute} - fetches a value from the cloud provider, eg. aws_availability_zones
* DevOps - cross-cutting practice between development (software creation) and operations (software deployment and maintenence); shown in practice to reduce lead times, reduce production incidents, reduce dev costs, and enable more frequent deployments
* Heredoc Syntax - for multi-line strings
* IAC - infrastructure as code; four broad categories of tools are ad-hoc scripts, configuration management, server templating, and server provisioning
* Immutable Infrastructure - when server configuration never changes post-deployment, so that server behaviour is easier to reason about; enabled by server templating
* Implicit Dependency - Terraform recognizes when on resources references the attribute of another resource and builds a dependency graph, affects the deployment plan
* Input Variable - used by syntax ${var.name}, Terraform uses these to share configuration across scripts; three types are string, list, and map; can have default value, otherwise Terraform will prompt
* Interpolation Function - Terraform can run some functions in script, eg. `${format(format_str, args)}` will format a string, uses same format logic as golang
* Interpolation Syntax - ${stuff}, used to look up Terraform resource attributes, variables
* Joel Test - Joel Spolky's simple test for project health
* Kernel Space - memory and privileges that the OS runs in, has direct control over computer hardware
* Launch Configuration - Terraform settings required to provision an ASG
* Lifecycle Block - Terraform settings that describe how to recreate resources, eg. create_before_destroy
* Master Server - required by Chef, Ansible, and SaltStack; deployment commands are coordinated by a central server; Terraform is masterless in the sense that the capability to support Terraform deployments is provided by the cloud providers that support it
* Out-of-Band Resources - when resources are created outside of Terraform
* Output Variable - allows resources to set variable values, eg. capture the ip address of a provisioned db server; the "terraform output" command will display all output values, although they are also shown at the end of a terraform apply
* Private Subnet - default VPC deployment option is public subnet so that new resources are accessible publicly, but in a real deployment a private subnet is a better security option
* Readme Driven Development - when you start with the readme
* Semantic Versioning - version numbers of the format major.minor.patch, where major releases tend to break backward compatibility, minor releases add features, and patches fix bugs
* Server Provisioning Tools - Terraform, CloudFormation, OpenStack Heat; not only configure servers, but create them as well; typically provisions entire platforms including web servers, load balancers, databases, anything else needed
* Server Templating Tools - Docker, Packer, Vagrant; spin up server based on a pre-build image, typically either VM or container, generally idempotent and enable immutable infrastructure
* Snowflake Servers - servers that require special attention; typical result of configuration drift
* Ternary Operator - `${condition ? value if true : value if false}`
* tfvars file - defines variables values, use with -var-file cli parameter
* Transparent Portability - when the same deployment plan works regardless of cloud provider; Terraform does not support this since the server options offered by AWS vs Azure and other providers differ too much
* User Space - memory and privileges that most applications run in, has to talk to the kernel in order to perform system operations
* Versioned Modules - can separate currently deployed version from the in-dev version; config files can have a module source be a git url, mercurial url, or http url
* Virtual Machine (VM) - VMWare, VirtualBox, Parallels; emulates underlying hardware, allows machine images to run in isolation, relies on a hypervisor
* Zero-Downtime Deployment - uses create_before_destroy lifecycle block, spins up new instances behind the ELB before destroying the old ones

# Techs

* AMI - Amazon Machine Image
* Ansible
* Ansible Playbook - script for Ansible, configures servers in parallel but can be set for serial / rolling deployment
* ARN - Amazon Resource Name
* ASG - Amazon Auto-Scaling Group
* Busybox tool
* Chef
* CloudWatch alarm - alerts based on metrics, can be defined in Terraform config
* DigitalOcean
* Docker
* EC2 - Amazon Elastic Cloud Compute
* ELB - Amazon Elastic Load Balancer
* Go - golang is what Terraform is written in
* Gruntwork.io - Terraform script repo, where the author worked
* HCL - HashiCorp Configuration Language; Terraform config is either this or a JSON format
* IAM - Amazon Identity and Access Management
* OpenStack Heat
* Packer
* Parallels
* Puppet
* RDS - Amazon Relational Database Service
* SaltStack
* Terraforming - tool for bulk Terraform import
* Terragrunt - wrapper project that uses DynamoDB to manage state
* Unix nohup command
* VirtualBox
* VMWare
* VPC - Amazon Virtual Private Cloud; ideally one for each environment (dev, staging, prod)

# Code

```
variable "user_names" {
  description = "List of users to create"
  type = "list"
  default = ["neo", "trinity", "morpheus"]
}

resource "aws_iam_user" "users" {
  count = "${length(var.user_names)}"
  name - "${element(var.user_names, count.index)}"
}
```

```
// only create a resource if the instance type is t-something (eg. t2.micro)
count = "${format("%.1s", var.instance_type) == "t" ? 1 : 0}"
```

```
// only create a resource if not foo
count = "${1 - var.foo}"
```

# See Also

* Dev Ops Handbook - book by IT Revolution Press, Gene Kim, Jez Humble, John Willis, Patrick Debois
* Kief Morris - Using Pipelines to Manage Environments with Infrastructure as Code
* Nick Dellamaggiore interview in Hello Startup
* Paul Hinze - helped with zero-downtime deployment method
