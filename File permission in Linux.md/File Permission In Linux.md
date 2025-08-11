# File Permissions in Linux
___________________________

## Project Overview
The research team at my organization needed to adjust file permissions for certain files and directories within the `projects` folder. The current permissions did not accurately match the level of access that should be granted. Reviewing and updating these permissions is important to maintain system security.

To address this, I completed the following steps:

=============================================================================

### 1. Viewing File and Directory Details
The command below shows how I checked the existing permissions for a specific directory in the file system:






<img width="666" height="326" alt="permission details" src="https://github.com/user-attachments/assets/48e692ae-bdf3-45cc-a606-f134e98bac01" />



### Understanding the Output

In the screenshot, the first line shows the command I entered, while the lines below display the output. This command lists everything inside the `projects` directory. I used:ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.

==============================================================================

### 2. Describing the Permissions String

The 10-character permissions string in Linux can be broken down to determine who can access a file and what actions they are allowed to perform. Here’s what each part means:

1. **1st character** – Indicates the file type:  
   - `d` → Directory  
   - `-` → Regular file  

2. **2nd–4th characters** – Show **read (r)**, **write (w)**, and **execute (x)** permissions for the **user** (file owner).  
   - A hyphen `-` means that permission is not granted.  

3. **5th–7th characters** – Show read, write, and execute permissions for the **group**.  
   - A hyphen `-` means that permission is not granted.  

4. **8th–10th characters** – Show read, write, and execute permissions for **others** (everyone else on the system).  
   - A hyphen `-` means that permission is not granted.  

---

### Example

For example, the file permissions for `project_t.txt` are: -rw-rwr--

Here’s what this means:
- **`-`** (1st character) → This is a file, not a directory.  
- **`rw-`** (2nd–4th) → The **user** has read and write permissions.  
- **`rw-`** (5th–7th) → The **group** has read and write permissions.  
- **`r--`** (8th–10th) → **Others** have read-only permissions.  
- No execute (`x`) permissions are granted to anyone.

=============================================================================

### 3. Change File Permissions

The organization decided that **others** should not have write access to any of their files. To follow this requirement, I reviewed the file permissions I had previously listed and found that `project_k.txt` needed its write access removed for others.




<img width="666" height="213" alt="change permission" src="https://github.com/user-attachments/assets/70b537a9-50e5-49fa-903d-107dcb9380cc" />


### Understanding the Commands

In the screenshot, the first two lines show the commands I entered, and the remaining lines display the output from the second command.  

- **`chmod`** → Changes permissions on files and directories.  
- **First argument** → Indicates which permissions to change.  
- **Second argument** → Specifies the target file or directory.  

In this example, I removed write permissions for **others** on the file `project_k.txt`:


chmod o-w project_k.txt

=============================================================================

### 4. Change File Permissions on a Hidden File

The research team at my organization recently archived `project_x.txt`. They decided that no one should have write access to this project, but the **user** and **group** should still have read access.



<img width="666" height="208" alt="change permission hidden file" src="https://github.com/user-attachments/assets/a7067a23-8f6b-427b-a19a-4ae782e42465" />

### Understanding the Commands

In the screenshot, the first two lines show the commands I entered, and the remaining lines display the output of the second command.

I know `.project_x.txt` is a hidden file because its name starts with a period (`.`).

In this example:
- I removed write permissions from the **user** with `u-w`.
- I removed write permissions from the **group** with `g-w`.
- I added read permissions to the **group** with `g+r`.

These changes adjusted the file permissions accordingly.

==============================================================================

### 5. Change Directory Permissions

My organization wants only the user `researcher2` to have access to the `drafts` directory and everything inside it. This means that no other users should have execute permissions on this directory.


<img width="662" height="209" alt="change permission of directory" src="https://github.com/user-attachments/assets/6a28c35c-6cf0-400a-9bc1-c2700dd4d18b" />


### Interpreting the Output

The output displays the permission listings for several files and directories: 

- **Line 1**: The current directory (`projects`)  
- **Line 2**: The parent directory (`home`)  
- **Line 3**: A regular file named `.project_x.txt`  
- **Line 4**: The `drafts` directory with restricted permissions  

You can see that only the user `researcher2` has execute permissions on the `drafts` directory. Previously, the group had execute permissions, so I used the `chmod` command to remove them. Since `researcher2` already had execute permissions, no changes were needed for that user.

==============================================================================

# Summary

I updated multiple permissions to align with the authorization levels my organization required for files and directories within the `projects` directory.  

The first step was using the `ls -la` command to review the current permissions. This helped guide my decisions for the next steps.  

I then used the `chmod` command several times to modify the permissions on various files and directories accordingly.








