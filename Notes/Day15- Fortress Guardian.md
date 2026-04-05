# Creating a Secure file for a new project
# Tasks
1. Create a new, empty file named `project_keys.txt` inside the `~/project/phoenix_project directory.`
   
2. Set the permissions for this file so that only the owner has `read and write access`, and no one else (not even users in the same group) has any access.

# Requirements
1. The file must be named `project_keys.txt.`

2. The file must be located at `~/project/phoenix_project/project_keys.txt.`
   
3. Use the `chmod` command with numeric notation to set the permissions.

# Solution:
`pwd`

`touch ~/project/phoenix_project/project_keys.txt.`

`chmod 600 ~/project/phoenix_project/project_keys.txt.`

`ls -l ~/project/phoenix_project/.`

# Assigning Ownership of Project Resources
# Tasks
Change the owner of the `~/project/phoenix_project` directory and all its contents to the user dev_lead.

Change the group owner of the `~/project/phoenix_project` directory and all its contents to the developers group.

# Requirements
1. The user owner must be dev_lead.

2. The group owner must be a developer.
   
3. The ownership change must apply recursively to all files and subdirectories within ~/project/phoenix_project.
   
4. You must use the chown command.

# Solution:
`sudo chown -R dev_lead:developers ~/project/phoenix_project.`

`ls -ld ~/project/phoenix_project.`

`ls -l ~/project/phoenix_project.`

# Securing the Main Project Directory
# Tasks
1. Set the permissions for the `~/project/phoenix_project directory.`

# Requirements
1. The owner (dev_lead) must have read, write, and execute permissions.
   
2. The group (developers) must have read and execute permissions.
   
3. Others must have no permissions.

Use the `chmod` command to apply these permissions to the `~/project/phoenix_project` directory itself (not recursively).

Since the directory is owned by `dev_lead`, you may need to use `sudo` to change permissions.


# Solution: 
`chmod 750 ~/project/phoenix_project.`

`ls -ld ~/project/phoenix_project/.`

# Setting Up Collaborative Permissions for the Dev Team
# Tasks
1. Set a special permission on the `~/project/phoenix_project/src` directory that forces all new files and subdirectories created within it to inherit the group ownership from the src directory itself (which is developers).

# Requirements
1. The solution must ensure new files in `~/project/phoenix_project/src` are automatically owned by the developers group.
   
2. You must use the chmod command to set this special permission.

3. You may need to use sudo to set permissions on directories owned by other users.

# solution:
`sudo chmod 2770 ~/project/phoenix_project.src.`

`ls -ld ~/project/pjoenix_project.src.`

