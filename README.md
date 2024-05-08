# Ansible Collection - morpheus.utilities

## Purpose
This Ansible code is intended to help install a few  in initial utilies that Morheus Tasks/Scripts may rely on.  This can target an inventoried Morpheus, or other systems as needed.

**Note:** This code assumes to always pull latest.  You may have more standarized approaches to installation.

## Installers Included
* Ansible
* Azure CLI (PowerShell)
* GCP SDK
* PowerShell Core
* TerraForm
* VMware PowerCLI (PowerShell)

## How to Use
1. Add `Ansible` integration in Morpheus to this GitRepo:  
        **NAME:** `Morpheus Utilities`  
        **Ansible GIT URL:** `https://github.com/BungeBash/morpheus.utilities.git`  
        **DEFAULT BRANCH:** `main`  
        **PLAYBOOKS PATH:** `/`  
        **ROLES PATH:** `/roles`  
        **GROUP VARIABLES PATH:** `/`  
        **HOST VARIABLES PATH:** `/`  
        **USE MORPHEUS AGENT COMMAND BUS:** `TRUE`  

2. Add `Task` type `Ansible`:  
        **ANSIBLE REPO:** `Morpheus Utilties`  
        **GIT REF:** `main`  
        **PLAYBOOK:** `install_utilities.yml`  
        **COMMAND OPTIONS:** (Define these to which installers are desired)  
        `--extra-vars '{"powershell":true,"azure_cli":true,"vmware_powercli":true,"gcp_sdk":true,"terraform":true,"ansible":true}'`  
        **EXECUTE TARGET:** `Resource`  

3. Run `Task`  