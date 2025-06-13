# Databricks: Unity Catalog

## Introduction

This project documents the process in setting up unity catalog and implementing medallion architecture in Databricks.

## Services Used

- Azure Databricks
- Access Connector for Azure Databricks
- Azure Data Lake Storage Gen 2

## Getting Started

### 1. Setting up Storage Containers

- Create 3 storage containers
  - One is for the metastore root
  - One is for the managed tables
  - One is for unmanaged datasets

![image](https://github.com/user-attachments/assets/139ae8a1-171e-499b-abc5-9d5f00160c4c)

### 2. Setting up Access Connector for Azure Databricks

- Provision the Access Connector for Azure Databricks
  ![image](https://github.com/user-attachments/assets/ca0e1972-322d-41ae-b831-f2467dd3c1f8)
- Ensure to select the same region as the storage containers
- Assign the Storage Blob Data Contributor to the managed identity of the connector

### 3. Setting up Unity Catalog

- Go to the Azure Databricks Account Console

  ![image](https://github.com/user-attachments/assets/1bae207f-e28e-4c79-9ba3-e8cf06379553)
- Create a new metastore
 - Ensure to select the same region as the databricks workspace and storage containers
 - Fill in the ADLS2 storage path using one of the storage containers created previously
 - Fiil in the subscription ID of the Access Connector created previously
![image](https://github.com/user-attachments/assets/fa43c67c-ab34-48f9-80e1-e0f13ebbed17)
- Set up the users and groups accordingly

  ![image](https://github.com/user-attachments/assets/cf1d2316-4aec-4643-942a-30c478cce3c4)
- Assign the users/groups to the required databricks workspace
![image](https://github.com/user-attachments/assets/970b435d-c1e5-492c-a18b-60da45df1a92)


## Resources

- [Udemy: Databricks - Master Azure Databricks for Data Engineers](https://www.udemy.com/course/master-azure-databricks-for-data-engineers/)
