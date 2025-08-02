# Recovery Access Control via RBAC

Implemented scoped access for VM recovery operations using Azure Role-Based Access Control (RBAC). Verified that only users with proper permissions can restore a deleted VM from Recovery Services Vault.

## User & Role Setup

- Created a **custom group** (`BackupAdmins`) with Backup  and added a user
  
  ![Admins](screenshots/backupAdmins-members.png)
  
- Created a **test user** in Microsoft Entra ID with only Reader access
  
  ![Roles](screenshots/backup-contributor-role.png)

## Deleted and Recovered VM

  ![vm delete](screenshots/delete-vm.png)

  
 - BackupAdmins group member is permitted to restore VM

![recovery-permitted](screenshots/restore-vm-settings.png)  


- Backup completed and a new VM is created by restoring old VM

  ![New VM](screenshots/recovered-vm.png)  
  
 - VM recovery with test user — restore blocked due to missing permissions
 
>  **Error Received**  
![access-denied](screenshots/test-user-access-denied.png)








