# File-Shares-and-Permissions

Create some sample file shares with various permissions
Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
Connect/log into Client-1 as a normal user (mydomain\<someuser>)
On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”
![image](https://github.com/user-attachments/assets/806388df-f770-43f4-95d1-dd290b8dd7df)

Set the following permissions (share the folder)
Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
(Skip accounting for now)
![image](https://github.com/user-attachments/assets/b9f4d3b0-033d-4a12-90cf-15f3e1164dc0)

![image](https://github.com/user-attachments/assets/e0cf63a1-47a6-47c2-bfc7-b82a6a292e10)

![image](https://github.com/user-attachments/assets/ee2cfe24-12b7-4d27-bb83-31f61ab8ae68)



Attempt to access file shares as a normal user
On Client-1, navigate to the shared folder (start, run, \\dc-1)
Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? Does it make sense?
![image](https://github.com/user-attachments/assets/777dc73f-bfb6-45d7-9c2d-f27afb2a2af4)

![image](https://github.com/user-attachments/assets/0a3f21df-9ea9-4f72-92b3-eeee84b9dc29)

![image](https://github.com/user-attachments/assets/1870d498-46b5-41b3-b683-47b0e7b1ba2f)




Create an “ACCOUNTANTS” Security Group, assign permissions, an test access
Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
On the “accounting” folder you created earlier, set the following permissions:
Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”
On Client-1, as  <someuser>, try to access the accountants folder. It should fail. 
Log out of Client-1 as  <someuser>
On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?

![image](https://github.com/user-attachments/assets/a419c62f-b6e1-4f25-9e2e-e88a9fee4c15)

![image](https://github.com/user-attachments/assets/a8288c8e-4436-4e24-95b2-0ae1d33339ff)

![image](https://github.com/user-attachments/assets/f33ab01c-1b0c-47a5-a2a0-4272b9cd855f)

![image](https://github.com/user-attachments/assets/43cdac3c-7166-49d4-947b-49eb7e1e9eb9)

