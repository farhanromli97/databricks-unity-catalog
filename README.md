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

- Provision the Access Connector for Azure Databricks resource
![image](https://github.com/user-attachments/assets/ca0e1972-322d-41ae-b831-f2467dd3c1f8)
- Ensure to select the same region as the storage containers
- Assign the Storage Blob Data Contributor to the managed identity of the connector

## Resources

- [Udemy: Databricks - Master Azure Databricks for Data Engineers](https://www.udemy.com/course/master-azure-databricks-for-data-engineers/)
