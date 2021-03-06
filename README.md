<p align="center"><img src="images/k8s-header.png"></p>

# NetApp Trident Bootcamp

## Trident with Kubernetes

This bootcamp requires the [NetApp Lab-on-Demand](https://labondemand.netapp.com/) "Trident with Kubernetes and ONTAP v3.1" lab which comes with Trident 19.07 already installed on Kubernetes 1.15.3. The provided [configure_bootcamp.sh](trident_with_k8s/deploy/configure_bootcamp.sh) within this repo will modify the environment to be ready for the tasks within this bootcamp to be carried out.

The same lab is also available to NetApp customers via the [Hands On Lab portal](https://handsonlabs.netapp.com/lab/trident) and again, you will need to run the [configuring bootcamp task](trident_with_k8s/tasks/configure_bootcamp) to get the standard Trident lab into the setup required for this bootcamp.

**If you are taking part in a NetApp hosted bootcamp, the configure_bootcamp.sh script may be run by the NetApp Lab On Demand team ahead of you connecting to the lab environment, so please confirm this with the person running your particular bootcamp.**  If the script has not been run, it can take ~20 minutes to complete, so please run it now by following the instructions [here](trident_with_k8s/tasks/configure_bootcamp) where you will also find details of the tasks carried out by the script.

This repository was orginally forked from the great work done by [YvosOnTheHub](<https://github.com/YvosOnTheHub/LabNetApp>). The bootcamp was further augmented by automating the building of the customized lab setup by way of shell scripts and Ansible playbooks as initially set out by [pablogarciaarevalo](<https://github.com/pablogarciaarevalo/demo-trident>). Many thanks also to [MrStevenSmith](<https://github.com/MrStevenSmith/Trident-WordPress-Application>) for his Trident based WordPress contribution :clap:  

## Bootcamp Environment Diagram

<p align="center"><img src="images/lab-diagram.png"></p>

To familiarise yourself with the environment and check that everything is ready for you to begin, please follow the instructions in [the first task](trident_with_k8s/tasks/verify_lab).  Once you are happy with your lab, you can choose to jump into any of the tasks listed below.  They do not need to be followed in any particular order, but if persistent storage is a new concept for you within k8s, it is recommended to follow them one-by-one.  If you do jump ahead, any pre-requisite tasks will be called out for you.

### K8s and Vim Commands

You will be using Vim to edit configuration files as part of this bootcamp.  If you are unfamiliar with Vim, a [basic set of instructions](trident_with_k8s/tasks/vim) has been created for you to keep open in a separate browser tab for reference

There is also a set of [useful k8s commands](trident_with_k8s/tasks/useful_commands) available in case you need them during the bootcamp.  Again, it may be worthwhile having these open in a separate browser tab for easy reference.

---------

### Verify Your Environment

Before you jump into any of the Production or Development cluster tasks you will need to verify that your environment setup has worked and it is ready for you to deploy applications.  A guide has been provided below, so please follow this and then return to this page to get started:

* [Verify and navigate the lab environment](trident_with_k8s/tasks/verify_lab)  

### Prod k8s Cluster Tasks

To give you a view of utilising a k8s cluster already configured with Trident, a number of tasks have been provided that can be run against the Production cluster.  If you would prefer to set up your own Trident install and configure storage backends and storageclases, a set of Development cluster tasks are provided further down on this page.

If you are new to Kubernetes or persistent storage for k8s, it is **highly recommended** to carry out the File Application task first, as this will give you a grounding in the basics.

* [Deploy your first application with File storage](trident_with_k8s/tasks/file_app)  

After you have verified your lab and carried out your first application deployment with persistent storage, below are a selection of tasks that will help get you more familiar with both k8s and persistent storage using NetApp Trident.  You don't have to carry out these tasks in order, but they are ordered in a way that would give the most logical flow. If there are any that are of particular interest though, feel free to skip ahead:

* [Deploy your first application with Block storage](trident_with_k8s/tasks/block_app)  
* [Use the 'import' feature of Trident](trident_with_k8s/tasks/pv_import)  
* [Consumption control with quotas](trident_with_k8s/tasks/quotas)  
* [Resize an NFS PVC](trident_with_k8s/tasks/resize_file)  
* [Using Virtual Storage Pools](trident_with_k8s/tasks/storage_pools)  
* [StatefulSets & Storage consumption](trident_with_k8s/tasks/statefulsets)  
* [Resize an iSCSI PVC](trident_with_k8s/tasks/resize_block)  
* [On-Demand Snapshots & Cloning PVCs from Snapshots](trident_with_k8s/tasks/snapshots_clones)  
* [Dynamic export policy management](trident_with_k8s/tasks/dynamic_exports)  

---------

### Dev k8s Cluster Tasks

If you would like to carry out some of the tasks performed for you by the configure_bootcamp.sh script, below are the commands required.  These can be useful if you wish to become familiar with tasks such as installing Trident or defining storage classes and should be run against the dev cluster via host **rhel5**:

* [Install Trident with an Operator](trident_with_k8s/tasks/trident_install)  
* [Upgrading with the Trident Operator](trident_with_k8s/tasks//trident_upgrade)  
* [Install Prometheus & incorporate Trident's metrics](trident_with_k8s/tasks/config_prometheus)  
* [Configure Grafana & add your first graphs](trident_with_k8s/tasks/config_grafana)  
* [Configure your first NAS backends & storage classes](trident_with_k8s/tasks/config_file)  
* [Configure your first iSCSI backends & storage classes](trident_with_k8s/tasks/config_block)  
* [Specify a default storage class](trident_with_k8s/tasks/default_sc)  
* [Prepare ONTAP for block storage on dev cluster](trident_with_k8s/tasks/ontap_block)  

---------
**Page navigation**  
[Top of Page](#top) | [Home](/README.md) | [Full Task List](/README.md#prod-k8s-cluster-tasks)
