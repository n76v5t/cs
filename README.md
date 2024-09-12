java cActive Directory Server
Build Document
Prepared for:	Lean Development Pty Ltd
Document Control

Document Details

Document category	Server build document
Template version	1.0
Title	Active Directory Server Build Document
Prepared by	MP Tech Solutions Ltd
Responsible System Engineer	John Smith
Project Management Consultant	Emily Davis
Client	Lean Development Pty Ltd

Change Record

Version	Change Description	Date	Author
1.0	Initial Server Build documentation	2024-09-09	MP Tech Solutions Ltd

Related Documents
Document	Version	Why Referenced?	Source / Location
Active Directory Server Design for Lean Development Pty Ltd	1.0	Design document	Electronic copy via email

1.Purpose of Document
Lean Development Pty Ltd (LD) is in the process of upgrading their network and server infrastructure. As part of this upgrade, MP Tech Solutions Ltd (MP Tech) deployed a new Active Directory server into the environment. 
This document presents a record of the configuration and system settings of the server at the time of handover to LD. 
2.Virtualisation Environment
Existing LD virtualisation infrastructure was used for deploying the server. This environment (performance and capacity) is able to cater for all infrastructure requirements stipulated in the design document. 
3.Network environment
The server will operate on the following subnet: 

Details of the subnet the server is located on
Server subnet (CIDR notation):	192.168.1.255
Gateway:	192.168.1.1

4.Virtual Machine Settings
The Virtual Machine (VM) resources and settings are presented in the table below. 

Virtual Machine Details (Hypervisor settings)
General Information
Virtual Machine Name:	VM-001
Operating System Type:	Linux
Operating system Version:	Ubuntu 20.04 LTS
System Information
Base Memory:	8 GB
System Processor(s) count:	4 CPUs
Storage 
Controller: Name:	SATA Controller
Virtual Disk Device 1 (OS disk): 
Type ([storage] format):
Virtual Size:
Details:
Location:	VMDK (Virtual Machine Disk)
50 GB
OS installation disk
/vm/disks/os-disk1.vmdk
Virtual Disk Device 2 (data disk): 
Type ([storage] format):
Virtual Size:
Details:
Location:	VMDK (Virtual Machine Disk)
100 GB
Data storage disk
/vm/disks/data-disk2.vmdk
Virtual Disk Device 3 (data disk): 
Type ([storage] format):
Virtual Size:
Details:
Location:	VMDK (Virtual Machine Disk)
200 GB
Backup and archive disk
/vm/disks/data-disk3.vmdk
Virtual Disk Device 4 (optional data disk): 
Type ([storage] format):
Virtual Size:
Details:
Location:	VMDK (Virtual Machine Disk)
150 GB
Log storage disk
/vm/disks/data-disk4.vmdk
	
Virtual Disk Device 5 (optional data disk): 
Type ([storage] format):
Virtual Size:
Details:
Location:	VMDK (Virtual Machine Disk)
250 GB
Optional disk for future use
/vm/disks/data-disk5.vmdk
CD/DVD drive [Yes/No]	Yes
Network 
Adapter 1: Attached to:	Bridged Adapter (Attached to physical network)

5.Computer Settings
1.2.3.4.5.5.1.General Settings
General settings as recorded in ‘Control Panel / System’ are presented below:

  Open Control Panel:
Press Windows Key + S and type "Control Panel" to open it.
  Navigate to System:
In the Control Panel, click on System and Security, then select System.
Alternatively, you can press Windows Key + Pause/Break to directly open the "System" window.
  Take a Screenshot:
Press PrtScn (Print Screen) to capture the screen, or use Windows Key + Shift + S to open Snipping Tool and select the area of the window.
  Insert Screenshot:
Paste it into the document by pressing Ctrl + V in the designated cell or space.

5.2.Logical Network Settings
Network and adapter and IP settings is provided using the command ‘ipconfig /all’:

  Log in to the Server:
Access W99-SERVER2-DC or the relevant server you are working on.
  Open Command Prompt:
Press Windows + R, type cmd, and press Enter.
Alternatively, search for Command Prompt in the Start menu and select Run as Administrator.
  Run the Command:
Type the following command and press Enter:
bash
Copy code
ipconfig /all
  Capture the Screenshot:
Once the output is displayed, press Alt + PrtScn (Print Screen) to capture the active window, including the VM title bar.
Open Paint or Word, paste the screenshot using Ctrl + V, and save the image.
  Insert the Screenshot in Your Document:
Open your document, navigate to the light blue cell area where the screenshot needs to be placed.
Insert the image or paste it directly into the document.

5.3.Logical Storage
Listing of disks and volumes is provided using the PowerShell command set:
Hostname ; Get-Volume


Open PowerShell:

Press Windows Key + X and select Windows PowerShell (Admin) to run PowerShell with administrative privileges.
Run the Command:

Type the following command and press Enter:
mathematica
Copy code
Get-Volume
This will display a list of disks and volumes on the server, showing information such as the volume label, file system, size, and health status.

Take a Screenshot:

After the command finishes displaying the information, press PrtScn (Print Screen) or use Windows Key + Shift + S to capture the screen with the output.
Insert Screenshot:

Paste the screenshot into the document by selecting the cell below the line and pressing Ctrl + V.

6.Roles and Features Installed
Listing of all roles and features installed on the server is provided using the PowerShell command set:
Hostname ; Get-WindowsFeature | where-object {$_.Installed -eq $True}


  Press Windows Key + X and choose Windows PowerShell (Admin) to run PowerShell with administrative privileges.
  Run the Command:
Type the following command and press Enter:
powershell
Copy code
Get-WindowsFeature | Where-Object {$_.Installed -eq $True}
This will display all the roles and features that are currently installed on the server.
  Take a Screenshot:
Once the command output is fully displayed, press PrtScn (Print Screen) or use Windows Key + Shift + S to capture the screen with the results.
  Insert Screenshot:
Paste the screenshot into your document by pressing Ctrl + V in the designated cell below the line.

7.Core Network Services
6.7.7.1.DNS
DNS is installed on the server and all zones are integrated with Active Directory (AD). Listing of all DNS zones is provided using the PowerShell command:  
Get-DnsServerZone

  Log in to the Server:
Access W99-SERVER2-DC or the relevant server where DNS is installed.
  Open PowerShell as Administrator:
Press Windows + X and select Windows PowerShell (Admin).
Alternatively, search for PowerShell in the Start menu, right-click, and select Run as Administrator.
  Run the PowerShell Command:
Type the following command and press Enter:
powershell
Copy code
Get-DnsServerZone
  Capture the Screenshot:
Once the DNS zones are displayed, press Alt + PrtScn (Print Screen) to capture the active window (including the VM title bar).
Open Paint or Word, paste the screenshot using Ctrl + V, and save the image.
  Insert the Screenshot in Your Document:
Open your document, navigate to the light blue cell area where the screenshot needs to be placed.
Insert the image or paste it directly into the document.

7.2.DHCP
DHCP is installed on the server. Listing of all DHCP scopes is provided using the PowerShell command:  
Get-DhcpServerv4Scope

Open PowerShell:

Press Windows Key + X and select Windows PowerShell (Admin) to run PowerShell with administrative privileges.
Run the DHCP Scope Command:

Type the following command and press Enter:
powershell
Copy code
Get-DhcpServerv4Scope
This will list all the DHCP scopes configured on the server.

Take a Screenshot:

After the command displays the list of DHCP scopes, press PrtScn (Print Screen) or use Windows Key + Shift 代 写data、Python/Java
代做程序编程语言+ S to take a screenshot of the output.
Insert Screenshot:

Paste the screenshot into the document by selecting the designated area and pressing Ctrl + V.

8.Active Directory
8.8.1.Forest, Domain and Site
The server acts as Domain Controller (DC) and Global Catalog server. At this stage this DC holds all Operation Master roles. Listing of the Active Directory (AD) forest, domains and sites is provided using the PowerShell command:
Get-AdForest ; netdom query fsmo


  Log in to the Server:
Access W99-SERVER2-DC or the relevant domain controller.
  Open PowerShell as Administrator:
Press Windows + X and select Windows PowerShell (Admin).
Alternatively, search for PowerShell in the Start menu, right-click, and select Run as Administrator.
  Run the PowerShell Commands:
Type the following command and press Enter:
powershell
Copy code
Get-AdForest ; netdom query fsmo
  Capture the Screenshot:
Once the output is displayed showing the forest details and FSMO roles, press Alt + PrtScn (Print Screen) to capture the active window (including the VM title bar).
Open Paint or Word, paste the screenshot using Ctrl + V, and save the image.
  Insert the Screenshot in Your Document:
Open your document, navigate to the light blue cell area where the screenshot needs to be placed.
Insert the image or paste it directly into the document.

8.2.Organizational Units
The Organizational Unit (OU) structure reflects the stipulated system administration requirements. Listing of the OUs is provided using the PowerShell command:
Get-ADObject -Filter { ObjectClass -eq 'organizationalunit' }

  Open PowerShell:
Press Windows Key + X and select Windows PowerShell (Admin) or Windows PowerShell (Active Directory Module) if you are managing Active Directory remotely.
  Run the OU Listing Command:
Type the following command and press Enter:
powershell
Copy code
Get-ADObject -Filter { ObjectClass -eq 'organizationalunit' }
This will list all the Organizational Units (OUs) in the Active Directory.
  Take a Screenshot:
Once the list of OUs is displayed, press PrtScn (Print Screen) or use Windows Key + Shift + S to capture the screen with the results.
  Insert Screenshot:
Paste the screenshot into your document by pressing Ctrl + V in the designated area below the line.

8.3.Security Groups
The group structure reflects the security requirements of the divisions/departments of the organisation.  Listing of all Global security groups in AD is provided using the PowerShell command:
Get-ADGroup -filter {GroupScope -eq "Global"} | Select Name,DistinguishedName | Sort-Object Name

  Log in to the Server:
Access W99-SERVER2-DC or the relevant server where Active Directory is configured.
  Open PowerShell as Administrator:
Press Windows + X and select Windows PowerShell (Admin).
Alternatively, search for PowerShell in the Start menu, right-click, and select Run as Administrator.
  Run the PowerShell Command:
Type the following command and press Enter:
powershell
Copy code
Get-ADGroup -filter {GroupScope -eq "Global"} | Select Name,DistinguishedName | Sort-Object Name
  Capture the Screenshot:
Once the output is displayed listing the global security groups, press Alt + PrtScn (Print Screen) to capture the active window (including the VM title bar).
Open Paint or Word, paste the screenshot using Ctrl + V, and save the image.
  Insert the Screenshot in Your Document:
Open your document, navigate to the light blue cell where the screenshot needs to be placed.
Insert the image or paste it directly into the document.

8.4.Groups Policy Objects
Listing of all GPO’s in AD is provided using the PowerShell command:
Get-GPO -all | Select DisplayName,Owner | Sort-Object DisplayName

  Open PowerShell:
Press Windows Key + X and choose Windows PowerShell (Admin) or Windows PowerShell (Active Directory Module).
  Run the GPO Listing Command:
Type the following command and press Enter:
powershell
Copy code
Get-GPO -All | Select DisplayName,Owner | Sort-Object DisplayName
This will list all the Group Policy Objects (GPOs) in the Active Directory along with their display names and owners.
  Take a Screenshot:
After the command completes displaying the list, press PrtScn (Print Screen) or use Windows Key + Shift + S to capture the screen with the results.
  Insert Screenshot:
Paste the screenshot into your document by selecting the designated area below the line and pressing Ctrl + V.

9.Shared Folders
Listing of all shared folders on the server is provided using the PowerShell command:
net share

  Open PowerShell:
Press Windows Key + X and choose Windows PowerShell (Admin).
 Run the Command to List Shared Folders:
Type the following command and press Enter:
powershell
Copy code
net share
This will list all shared folders on the server.
 Take a Screenshot:
After the command displays the shared folders, press PrtScn (Print Screen) or use Windows Key + Shift + S to capture the screen.
 Insert Screenshot:
Paste the screenshot into your document by selecting the designated area below the line and pressing Ctrl + V.

10.Clean up and restore worksite 
Temporary and template VMs used during the server deployment were removed from the work environment. 
Listing of VMs on the host on completion of the project (using PowerShell prompt):
CD "C:\Program Files\Oracle\VirtualBox"
Note:	In the above command you must make sure that you specify the path where you have installed VirtualBox. 
whoami ; get-date ; .\vboxmanage list vms

  Log in to the Host Server:
Access the server or workstation where VirtualBox is installed.
  Open PowerShell as Administrator:
Press Windows + X and select Windows PowerShell (Admin).
Alternatively, search for PowerShell in the Start menu, right-click, and select Run as Administrator.
  Change Directory to VirtualBox Installation Folder:
If you installed VirtualBox in the default location, use this command:
powershell
Copy code
CD "C:\Program Files\Oracle\VirtualBox"
If you installed VirtualBox in a custom path, replace the path accordingly.
  Run the Commands to List VMs:
After navigating to the VirtualBox directory, run the following commands in sequence:
powershell
Copy code
whoami ; get-date ; .\vboxmanage list vms
  Capture the Screenshot:
Once the output is displayed showing the VMs, your username, and the date, press Alt + PrtScn (Print Screen) to capture the active window, including the VM title bar.
Open Paint or Word, paste the screenshot using Ctrl + V, and save the image.
  Insert the Screenshot in Your Document:
Open your document and navigate to the designated light blue cell where the screenshot needs to be inserted.
Paste the screenshot directly into the document.



Project Acceptance Sign Off 

Project 
Customer: 	Lean Development Pty Ltd
Project:  	Active Directory Server Deployment

Final status report	Select
Yes or No
Server design document has been produced and approved	Yes 
Agreed server services/applications are configured and operational	Yes 
Standard build documentation has been produced and approved	Yes 
Pre-production testing was successfully carried out	Yes 
Work site and network environment was left in order and to the client’s satisfaction	Yes
The work was finished within the agreed timeframe	Yes 

Server validation	Select 
Yes or No
Server was built and configured according to the given design specifications and meets the operational requirements	Yes 

Project completion acceptance	Select 
Yes or No
The project has been successfully completed	Yes 

MP Tech Solutions Ltd
…………………… / System Engineer	Date:    9/ 9/ 2024
MP Tech Solutions Ltd	

Lean Development Pty Ltd
…..…………..  / MP Tech - Project Management Consultant	Date:    9 / 9/ 2024
On behalf of Lean Development Pty Ltd representative	

         
加QQ：99515681  WX：codinghelp
