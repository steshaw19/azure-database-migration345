# Azure Database Migration Project
## Windows Virtual Machine Setup for Production Environment
This section documents the process of setting up a Windows Virtual Machine (VM) to serve as the cornerstone of the production environment. The VM emulates the functions of a Windows server, replicating the operations of an on-premise system within a company and provides a secure and dedicated data storage solution.

## VM Setup
The following information provides insight into how the VM was set up for this project. Before logging into the cloud, it is imperitive that two-factor-authorisation is enabled to prevent security breaches.

1. After logging into Microsoft Azure, AiCore Users was moved to the current directory by clicking the profile icon on the top right when in Azure & "switch directory". This allows access to the AiCore Cloud subscription to create resources.
2. Next, I navigated to the Virtual Machines section. The AiCore Cloud will be selected as default. Keep this setting and name the resource group to store the resources. In this case, the resource group was assigned `database-migration`to match the purpose of the project.
3. A name was assigned to the virtual machine and the closest location `UK South` was chosen. Defaults were kept for availibility options and zones, as well as the security type.
4. The type of machine and size was then chosen to be able to process the databases efficiently and effectively: `Windows 10 Pro, version 22H2 - x64 Gen2` and ` Standard_D4s_v3 - 4 vcpus, 16 GiB memory`
5. Finally, an administrator username and password was set and `RDP (3389)` inbound port was selected to allow a connection to a virtual machine.
6. Confirm the selection by clicking **review + create**. Once it has been validated, **create** can be clicked to begin deployment.

## Initiating VM
1. The first step is to open Remote Desktop Connetion on the local machine. This is installed as default on Windows devices.
2. Now, click **connect** on the virtual machine instance created in the previous setup.
3. Select **Native RDP**. Once it has validated, download the RDP file.
4. Open the RDP file and add the administrator username and password assigned in the previous setup.

## Installing SQL Server & SQL Server Management Studio (SSMS)
### SQL Server
1. Download the SQL Server [download wizard](https://go.microsoft.com/fwlink/p/?linkid=2215158&clcid=0x809&culture=en-gb&country=gb)
2. Run the file and choose basic setup.
### SSMS
1. Once the wizard has completed the installation, it provides an option to install SSMS. Clicking this will direct you to the Microsoft website. Download the file for SSMS 19.2 which includes Azure Data Studio installation.
2. When first opening SSMS, it requests that the server type, server name, and authentification type are assigned. This may be autofilled, and if this is the case you can leave as default. If not, set server type as `Database Engine`, server name as the name of the virtual machine, and choose `Windows Authentification` which is the username and password assigned when creating the virtual machine.

## Create the Production Database
This project uses the SQL Server Database [AdventureWorks](https://aicore-portal-public-prod-307050600709.s3.eu-west-1.amazonaws.com/project-files/93dd5a0c-212d-48eb-ad51-df521a9b4e9c/AdventureWorks2022.bak) to simulate a fictional manufacturing company's operations. First download the AdventureWorks database using the above link and then follow the steps below to restore the database on your server:
1. First, make sure that the `AdventureWorks` file is saved in the correct folder for restoration: `"C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\Backup"`
2. Open SQL Server Management Studio (SSMS) and connect to the SQL Server instance for the virtual machine.
3. Right-click on the Databases node in the Object Explorer, and then choose `Restore Database...`.
4. In the Restore Database window, choose the `Device` option and click the `...` button to select the backup files to restore. Click the `Add` button to navigate to the location of the backup files. Check that all the details of the file location are correct and then confirm. All tables and data should now be available to query.
