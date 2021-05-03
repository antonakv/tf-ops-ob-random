# sample repo - random (gh repo)

## Intro

This manual is dedicated to run terraform code with random provider

Tested on Mac OS X.

## Requirements

- Hashicorp terraform recent version installed
[Terraform installation manual](https://learn.hashicorp.com/tutorials/terraform/install-cli)

- git installed
[Git installation manual](https://git-scm.com/download/mac)

## Preparation 
- Clone git repository. 

```bash
git clone https://github.com/antonakv/tf-ops-ob-random.git
```

Expected command output looks like this:

```bash
Cloning into 'tf-ops-ob-random'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 12 (delta 1), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.
```

- Change folder to tf-ops-ob-random

```bash
cd tf-ops-ob-random
```

## Run terraform code

- In the same folder you were before run init

```bash
terraform init
```

Sample result

```bash
$ terraform init

Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/random...
- Installing hashicorp/random v3.1.0...
- Installed hashicorp/random v3.1.0 (self-signed, key ID 34365D9472D7468F)

Partner and community providers are signed by their developers.
If you d like to know more about provider signing, you can read about it here:
https://www.terraform.io/docs/plugins/signing.html

The following providers do not have any version constraints in configuration,
so the latest version was installed.

To prevent automatic upgrades to new major versions that may contain breaking
changes, we recommend adding version constraints in a required_providers block
in your configuration, with the constraint strings suggested below.

* hashicorp/random: version = "~> 3.1.0"

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.

```

- In the same folder you were before apply terraform code

```bash
$ terraform apply
```

Sample result
```bash
$ terraform apply

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # random_integer.number will be created
  + resource "random_integer" "number" {
      + id     = (known after apply)
      + max    = 1000
      + min    = 1
      + result = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

random_integer.number: Creating...
random_integer.number: Creation complete after 0s [id=31]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

```
