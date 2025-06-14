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

### 3. Setting up Unity Catalog Metastore

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


### 4. Setting up External Locations

- Go to External Data

  ![image](https://github.com/user-attachments/assets/45d969ca-e8bb-4fc0-a1c7-4c4ed2a398b1)
- Create a new external location
  - Provide the name 
  - Fill in the ADLS directory path
  - Fill in the storage credential
  ![image](https://github.com/user-attachments/assets/fa7bc57a-8a89-4886-9e20-d4e69f1501e6)
- Set up external locations accordingly using different directories
![image](https://github.com/user-attachments/assets/eea7a0af-c199-4033-a586-dea504e35a7d)
- Grant the necessary permissions to the users/groups for the external locations except for the ones to be used for catalog's storage location
  ![image](https://github.com/user-attachments/assets/ef5ed4ea-979f-4dad-a63f-65c1895da721)


### 5. Setting up Catalog

- Create a new catalog
  - Choose the relevant storage location based on the external locations created previously 
  ![image](https://github.com/user-attachments/assets/0649c4f8-d799-4d92-aeff-e4669681032d)
- Grant the necessary permissions to the users/groups
  ![image](https://github.com/user-attachments/assets/3909253a-80d3-4528-ad84-dc21089c9e01)



## Resources

- [Udemy: Databricks - Master Azure Databricks for Data Engineers](https://www.udemy.com/course/master-azure-databricks-for-data-engineers/)
