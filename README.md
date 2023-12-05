# terraform-storage-account

This story will teach us how to create storage accounts with Service Endpoint in Azure Vnet with Terraform. Here, We use a hierarchical namespace-enabled storage account which helps to use the Azure datalake feature as well.

A service endpoint is a setup that allows users to connect to Azure services directly using an Azure Virtual Network. You can use it to connect your virtual private network to Azure services without using the internet to route the traffic. So, We can use service endpoints to enhance the security and efficiency of our applications.

Microsoft Azure offers a networking solution called Azure Virtual Network (VNet) through its cloud computing platform. The Azure cloud lets you set up private, separate, and encrypted networks. With Azure Virtual Networks (VNets), you can set up a network of connections between your virtual machines, databases, and other services on Azure.

Azure Storage account is a storage service provided by Azure. Secure, scalable cloud storage is now at your fingertips with an Azure Storage Account, a service from Microsoft Azure. Accessible and manageable from any location with an internet connection, it acts as a central store for many kinds of data. Files, queues, blobs (binary big objects), and tables are among the many data types that Azure Storage can handle.

When it comes to Azure Storage, the term “hierarchical namespace” (HNS) refers to the organization of data within Azure Data Lake Storage Gen2 accounts in a hierarchical structure. Azure Blob Storage serves as the foundation for Azure Data Lake Storage Gen2, an extension of Azure Blob Storage that gives it additional capabilities, such as a hierarchical file system.

# Note: 
You can make use of the benefits of a hierarchical file system as well as the scalability of Azure Blob Storage when you create a storage account in Azure and enable the hierarchical namespace for Azure Data Lake Storage Gen2.
If you want to disable the hierarchical namespace of the storage account, you can remove it by “is_hns_enabled = false” in the configuration.

Creation of an Azure Storage Account with a Service Endpoint
The process to create the Azure Storage Account with service Endpoint requires several steps in this specific order:

1. Resource Group Creation
2. VNET Creation with service endpoints
3. Subnet Creation
4. Creation of a Storage Account by using the virtual network subnet ID

# Prerequisites
Familiar with Azure service provision
Familiar with Terraform

# Step 1 — init files and plan
terraform init && terraform plan

# Step 2 — Apply the configurations

terraform apply -var resource_group_name="resourcegroup" -var location="eastus" -var storage_account_name="storage_account_name"
After doing this step you can go through the Azure portal and see provisioned services.

If you want to remove all services that you have configured, You can use the below command.

# Step 3 — Destroying all services that you have provisioned.

terraform destroy -var resource_group_name="resourcegroup" -var location="eastus" -var
