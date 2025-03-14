### WORK CASE 3

### 1.Cloning a virtual machine and exporting the operating system.
since I I am working with the built-in Hyper-V hypervisor.
Since Hyper-V does not have a built-in cloning feature, we will carry out this process manually.

### We have a virtual machine, and to create a copy, we need to turn off the virtual machine that we want to duplicate. Next, locate the VHDX disk of the virtual machine and copy the VHDX file to a new location. After that, we click on the "Create" button and select "Virtual Machine."

###  creating a virtual machine
To begin, right-click on our device.


![image](https://github.com/user-attachments/assets/273c0650-68f2-49e8-bfce-25206f669f52)

### Once the new virtual machine is created, it's important to assign a name to it. Select a distinct name to ensure it is easily identifiable and separate from the original virtual machine.


![image](https://github.com/user-attachments/assets/bf40e819-0b67-4915-8db6-dff65bc3f795)


### Once we have assigned memory and set up the connections, we move on to indicate the file. We will utilize the VHDX file that we copied earlier. After that, we finish creating the virtual machine and launch it.

Transferring a Virtual Machine in Hyper-V
If you need to move a virtual machine to another computer or a different virtual environment, you can use the export and import features.

### How to Export a VM:
Open Hyper-V Manager.
Select the virtual machine, right-click on it, and choose "Export".
Specify the destination folder for saving the files (e.g., D:\ExportedVM\).
Wait for the process to complete.
How to Import a VM:
Launch Hyper-V Manager.
Click on "Import Virtual Machine".
Browse to the folder containing the exported VM (D:\ExportedVM\).
Follow the on-screen instructions to finalize the import.

![image](https://github.com/user-attachments/assets/8568ea59-0bdc-41d7-a313-5e51830d31e2)

### My older computer struggles to run two operating systems simultaneously, causing severe slowdowns and freezes. This makes task management difficult, leading to frequent delays and interruptions that hinder my productivity.


Here, we indicate the location of our original virtual machine


![image](https://github.com/user-attachments/assets/c74cd0f0-8d81-44c4-b1a4-784e16c1f4ec)

Here, we set the location for our primary virtual machine.


![image](https://github.com/user-attachments/assets/e85ee2fc-d6a3-48d6-bf14-dd71c0833b3c)

   Export the file.
![image](https://github.com/user-attachments/assets/6ccf7b83-fc19-48aa-9148-361d023aecde)

###       2.Hyper-V Network Connection Types
Hyper-V supports different network configurations for virtual machines:

1. NAT (Network Address Translation)
The virtual machine gains Internet access through the host’s network connection.
Other VMs cannot directly communicate with it.
2. Bridged (Network Bridge Mode)
The VM is assigned a real IP address from the router.
It operates as a standalone device in the local network.
3. Host-Only Network
The virtual machine can interact only with the host system.
No Internet access is provided.
4. Internal Network
Virtual machines within the same environment can communicate with each other.
The host does not have visibility or access to this network.
Open the VM settings.
In Hyper-V Manager, select the virtual machine.
Click on "Settings."

### Checking Internet Connection
Run the command in the terminal: ping youtube.com

![image](https://github.com/user-attachments/assets/72880537-1c8d-4f5b-b5ad-a99bae0c0581)


### Sending messages via netcat
On the first VM (192.168.1.50):


nc -l -p 1234  
On the second VM (172.24.207.57):

### echo "Hello from RPZ 23-A" | nc 172.24.207.57 
and we get the message

Verifying access via SSH
We enter the code into the first virtual machine.

sudo systemctl start ssh На другій ВМ підклаємося:

cloneVM@153.44.267.57

### Configuring a Shared Network Folder
Windows → Windows
First, create a folder (e.g., C:\SharedFolder).
Then, right-click → Properties → Sharing → Advanced Sharing.
Grant access to "Everyone – Full Control."
On the second VM, access:

\\192.168.1.50\SharedFolder  
Windows ↔ Linux (Samba)
Make sure sharing is enabled on Windows.
On Linux, you need to install Samba:


sudo apt install samba -y  
To connect to the Windows folder, use:


smbclient -L //192.168.1.50/SharedFolder -U user  




File Sharing Between the Host OS (Windows) and the VM
Method 1: Shared Folder
In Hyper-V Manager → Settings → Integration Services → Enable Guest Services.
Use Enhanced Session Mode and copy files via Drag & Drop.
Method 2: RDP (Remote Desktop)
Enable RDP access on the VM (sysdm.cpl → Remote).
Connect using mstsc from Windows.
Utilize the "Local Resources" option to access files.

Method 3: Built-in PowerShell Command
To copy a file to the VM:


### Copy-VMFile -Name "VMName" -SourcePath "C:\file.mp3" -DestinationPath "C:\Users\Public\" -CreateFullPath -FileSource Host  
To copy from the VM to the host:


Copy-VMFile -Name "VMName" -SourcePath "C:\Users\Public\document.docx" -Destina

### conclusions.

### In summary, the tasks outlined provide a comprehensive guide for setting up and managing virtual machines using Hyper-V. They cover essential aspects such as configuring network connections, sharing files between the host and virtual machines, and ensuring proper access through SSH and RDP. By following these steps, users can effectively utilize virtual environments for various applications and enhance their productivity.





