# Create a CI/CD pipeline and worw

**Type**: Group    
**Motivation**: Set up a basic (bare minimum) workflow for your CI/CD pipeline.

---

### Prequisite
You should have a running VM at Azure, and the VM should be updated and have the nessesary tools and apllications installed.      
You should know the ip address and have that ip address stored as a [**secret** on Github](../06._CI_github_actions/04._github_secrets.md#lets-set-secrets-through-the-gh-cli).    
You should have created [branch protection rules](../06._CI_github_actions/exercises/branch_protection_rules.md) for your repository.     

---

## Taks    
In your cookbook project, create a workflow file. 
This workflow should be triggered by a **PR** to master, or by a **manual execution** by you on GitHub in the **Actions** section.    
Your workflow should use **environment variables**. You need to handle and be able to use these.    
In the workflow you should **build** a Docker image, or images depending on you architechture, and this or these images should be pushed to ghcr.io.     
In the workflow you should **deploy** you application to your VM at Azure. For this you should transfere the relevat files via SCP.       
You also need to exercute commands on you VM on Azure. For this to work you should SSH into the VM, and then execute the commands nessesary to run you application.      




