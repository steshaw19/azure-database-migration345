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

## Opening VM on Local Machine





