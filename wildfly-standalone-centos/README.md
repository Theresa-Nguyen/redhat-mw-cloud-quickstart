# Java on Azure | Red Hat WildFly 18.0.1.Final on CentOS 8 (standalone mode)
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FSpektraSystems%2Fredhat-mw-cloud-quickstart%2Fmaster%2Fwildfly-standalone-centos%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FMicrosoft%2Fredhat-mw-cloud-quickstart%2Fmaster%2Fwildfly-standalone-centos%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

`Tags: WildFly, Red Hat, CentOS, Java, Java EE, Jakarta EE, Azure, Azure VM`

<!-- TOC -->

1. [Solution Overview ](#solution-overview)
2. [Template Solution Architecture ](#template-solution-architecture)
3. [Licenses and Costs ](#licenses-and-costs)
4. [Prerequisites](#prerequisites)
5. [Deployment Steps](#deployment-steps)
6. [Deployment Time](#deployment-time)
7. [Post Deployment Steps](#post-deployment-steps)
8. [Support](#support)

<!-- /TOC -->

## Solution Overview

This template creates a standalone node of WildFly on CentOS to a Standard F1 VM size in your Resource Group (RG) which includes a Public DNS, Private Virtual Network and security configuration. It is ideal for development and testing of enterprise Java applications on Azure. 

WildFly is an open-source application server runtime that is exceptionally fast, flexible, lightweight and powerful. It is Jakarta EE 8 Full Platform and Web Profile compatible.  The state-of-the-art architecture built on the Modular Service Container enables services on-demand when your application requires them.

This Azure quickstart template deploys a web applicaton on WildFly 18.0.1.Final running on CentOS 8.

The technology behind WildFly is also available in Red Hat JBoss Enterprise Application Platform (EAP), a hardended enterprise subscription with Red Hat's world-class support, long multi-year maintenance cyccles and exclusive content. JBoss EAP is an open-soure application server that you can download for free, for developement use.  To obtain a Red Hat Subscription Management (RHSM) account for JBoss EAP, go to: www.redhat.com 

## Template Solution Architecture 

This template creates all of the Azure compute resources to run WildFly 18.0.1.Final on top of CentOS 8.0. The following resources are created by this template:

- CentOS 8 VM 
- Public DNS 
- Private Virtual Network 
- Security Configuration 
- WildFly 18.0.1.Final
- Sample Java application deployed to WildFly

Following is the Architecture:
<img src="images/wildfly.arch.PNG" width="800">

To learn more about WildFly 18.0.0.Final, check out:
https://docs.wildfly.org/18/

## License, Subscription and Costs 

This template uses an Azure CentOS 8 image which is a Pay-as-you-go (PAYG) VM image and does not require the user to license. The VM will be licensed automatically after the instance is launched for the first time and user will be charged hourly in addition to Microsoft's Linux VM rates.  Click [here](https://azure.microsoft.com/en-gb/pricing/details/virtual-machines/linux/#red-hat) for pricing details. WildFly is free to download and use and does not require a Red Hat Subscription.

## Prerequisites 

1. Azure Subscription with specified payment method (CentOS-Based 8.0 is a marketplace product and requires payment method to be specified in the user Azure Subscription).

2. To create the VM, you will need:

    - **Admin Username** and password

    - **DNS Label Prefix** for the public IP

    - **WildFly Username** and password to enable the WildFly Admin Console and Deployment method

    - **SSH Key Data** which is a SSH RSA public key.  

## Deployment Steps  

Build your environment with WildFly 18.0.1.Final on top of CentOS 8.0 on Azure in a few simple steps:  

1. Launch the Template by clicking on the **Deploy to Azure** button.  

2. Complete the following parameter values. Then accept the terms and condition before clicking on the **Purchase** button.

    - **Subscription** - Choose the appropriate subscription where you would like to deploy.

    - **Resource Group** - Create a new Resource Group or you can select an existing one.

    - **Location** - Choose the appropriate location for your deployment.

    - **Admin Username** - User account name for logging into your CentOS VM.

    - **Admin Password** - User account password for logging into your CentOS VM.

    - **DNS Label Prefix** - DNS Label for the Public IP. Must be lowercase. It should match with the following regular expression: ^[a-z][a-z0-9-]{1,61}[a-z0-9]$ or it will raise an error.

    - **Wildfly Username** - Username for Wildfly Console Manager.

    - **Wildfly Password** - User account password for Wildfly Console Manager.

    - **SSH Key Data** - Generate an SSH key using Puttygen and provide the data here.

    - Leave the rest of the Parameter Value (artifacts and location) as is and proceed to purchase.

## Deployment Time 

The deployment takes less than 10 minutes to complete.

## Post Deployment Steps

- Once the deployment is successfull, go the VM and copy the Public IP of the VM.
- Open a web browser and go to **http://<PUBLIC_HOSTNAME>:8080/dukes/** and you should see the application running:

<img src="images/app.png" width="800">

- If you want to access the administration console go to **http://<PUBLIC_HOSTNAME>:8080** and click on the link Administration Console:

<img src="images/admin.png" width="800">

## Notes

If you're interested in Red Hat JBoss EAP Azure Quickstart templates, you can fine it as here:

*  <a href="https://github.com/Azure/azure-quickstart-templates/tree/master/jboss-eap-standalone-rhel7" target="_blank"> [Red Hat JBoss EAP on an Azure VM]</a> - Standalone JBoss EAP 7 with a sample web app on a RHEL 7 Azure VM.

*  <a href="https://github.com/Azure/azure-quickstart-templates/tree/master/jboss-eap-standalone-openshift" target="_blank"> [Red Hat JBoss EAP on OpenShift Container Platform on Azure RHEL VM]</a> - All-in-one OpenShift Container Platform 3 cluster and Red Hat JBoss EAP 7 with a sample web app.

## Support 

For any support related questions, issues or customization requirements, please contact info@spektrasystems.com

**** test change for restart build**
