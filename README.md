# Azure Database Migration Project Milestone Achievements README

## Overview

Welcome to the README file detailing the achievements in this project. In this document, I'll provide detailed insights into the project. 

### Project Diagram:
The following link provides a visual representation of the project.


[Lucid Flowchart](https://lucid.app/lucidchart/847765c6-6475-45be-a891-a164e176f618/edit?viewport_loc=-3893%2C-2034%2C3922%2C1582%2C0_0&invitationId=inv_56cfd0bf-2834-489f-9c9a-8e60ded42e51)

## Virtual Machine Setup

### 1. Azure Virtual Machine Configuration

The Virtual Machine (VM) setup is optimized for performance and security on the Azure cloud platform. Key configurations include appropriate VM sizing, networking settings, and security. SQL Server and SQL Server Management Studio (SSMS) were installed on the VM. Using VMs provides easy scalability when required and extra security and protection through Azure Cloud Services. 

## Azure SQL Database Migration & Configuration

### 1. Server Configuration

I configured the Azure SQL Database server with the appropriate resources, including vCores, storage, and memory, to meet the performance requirements of our application.

### 2. Security Measures

Implemented robust security measures, including firewall rules, Virtual Network Service Endpoints, and SQL authentification, to safeguard our database from unauthorized access.

## Data Migration Process

### 1. Assessment and Planning

Before migration, I conducted a thorough assessment of the existing database's tables and schema to identify dependencies, performance bottlenecks, and potential challenges. This information guided the migration plan.

### 2. Schema and Data Migration

Azure Database Migration Service was used to migrate the database schema and data. This automated process significantly reduced migration time and minimized manual errors.

### 3. Database Migration

The AdventureWorks database was successfully migrated from a localhost database to Azure SQL Database, ensuring minimal downtime and no data loss during the transition.

With Azure SQL Database, we have experienced improved performance and scalability, allowing our application to handle increased workloads and deliver a more responsive user experience.

## Backup Process

### 1. Meticulous Backup Strategy

A meticulous backup strategy to ensure the safety and integrity of our data was implemented. This strategy includes regular full backups and reports to minimize data loss and recovery time objectives.

### 2. Automated Maintenance Plans Configuration

I leveraged SQL Server Management Studio (SSMS) Maintenance Plans to automate the backup process. The plan is configured to execute a scheduled weekly full backup, which provides a hands-off approach to data protection. These backups are saved in Azure Data Storage containers and can be accessed, with their reports, through the Azure Portal.

### 3. Monitoring and Notifications

The maintenance Plans include monitoring and notification features to alert me in case of any backup failures or issues. This proactive approach allows me to address potential problems swiftly, ensuring the reliability of our backup strategy.

### 4. Azure Blob Storage Integration

Backups are securely stored in Azure Blob Storage, leveraging its durability and redundancy features. Azure Blob Storage provides a scalable and cost-effective solution for storing our critical data, with seamless integration into our backup and restoration processes.

### 5. Encryption and Access Controls

Utilizing Azure Blob Storage's encryption capabilities, we ensure that our backups are encrypted at rest and during transit. Access controls and role-based permissions are configured to restrict unauthorized access to the stored backups, enhancing overall data security.

### 6. Disaster Recovery

To test the backup strategy, disaster data loss was mimicked through deletion of key data using the code:

```SQL
UPDATE TOP(1000) Password.Person
SET PasswordHash = 0
```
The backup strategy enabled an efficient and successful restoration without any data loss.

### 7. Geo-Replication Setup

I configured geo-replication to ensure data redundancy and high availability across multiple geographic regions. Leveraging Azure SQL Database's built-in geo-replication features, we established replication links between the primary and secondary databases in different Azure regions.

### 8. Failover Resilience

Geo-replication proved highly effective in ensuring failover resilience. Automatic failovers were seamless and database connection was successful in both regions without data loss.

## Microsoft Entra ID

Finally, Microsoft Entra ID was utitlised to increase security and permissions of users. Admin and Reader accounts were created and tested to ensure the correct roles for each type of account.
