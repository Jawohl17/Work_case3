1.Cloning a virtual machine and exporting the operating system.
since I I am working with the built-in Hyper-V hypervisor.
Since Hyper-V does not have a built-in cloning feature, we will carry out this process manually.

We have a virtual machine, and to create a copy, we need to turn off the virtual machine that we want to duplicate. Next, locate the VHDX disk of the virtual machine and copy the VHDX file to a new location. After that, we click on the "Create" button and select "Virtual Machine."

creating a virtual machine
To begin, right-click on our device.
![image](https://github.com/user-attachments/assets/273c0650-68f2-49e8-bfce-25206f669f52)

Once the new virtual machine is created, it's important to assign a name to it. Select a distinct name to ensure it is easily identifiable and separate from the original virtual machine.
![image](https://github.com/user-attachments/assets/bf40e819-0b67-4915-8db6-dff65bc3f795)
Once we have assigned memory and set up the connections, we move on to indicate the file. We will utilize the VHDX file that we copied earlier. After that, we finish creating the virtual machine and launch it.

Transferring a Virtual Machine in Hyper-V
If you need to move a virtual machine to another computer or a different virtual environment, you can use the export and import features.

How to Export a VM:
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
Here, we indicate the location of our original virtual machine
![image](https://github.com/user-attachments/assets/c74cd0f0-8d81-44c4-b1a4-784e16c1f4ec)


