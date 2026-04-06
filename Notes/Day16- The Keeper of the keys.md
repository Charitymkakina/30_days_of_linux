# Onboarding a New Developer to the System
# Tasks
1. Create a new user account for Brenda Smith.

# Requirements
1. The username must be b.smith.
2. Use the appropriate command to add a new user to the system. You will need sudo privileges.

# Solution:
`sudo useradd -m b.smith.`

`grep "b.smith" /etc/passwd.`

# Creating a Dedicated Home Directory for the New User
# Tasks
1. Create a home directory for the user b.smith located at `/home/b.smith.`

# Requirements
1. The home directory must be created for the user b.smith.

2. You should use an option with the useradd command to create the home directory automatically. 

3. If you have already created the user without a home directory, you may need to delete the user first,
then recreate it correctly.

# Solution:
`sudo useradd -m -d /home/b.smith b.smith.`

`ls -la /home/.`

# Assigning an Initial Password for the New User
# Tasks
1. Set a password for the user b.smith.

# Requirements
1. Use the standard Linux command to change a user's password.
2. You will be prompted to enter and confirm the new password. You can use any simple password, for example, password123.

# Solution:
`sudo passwd b.smith.`

`sudo grep "^b.smith" /etc/shadow.`

# Adding the New Developer to the "developers" Group

# Tasks
1. Add the user b.smith to the developers group.

# Requirements
1. The user b.smith must be a member of the developers group.

2. The user's existing group memberships should not be removed.

# Solution:
`sudo usermod -aG developers b.smith.`

`groups b.smith.`

`id b.smith.`

`grep "developers:" /etc/group.`

# Temporarily Disabling a Departing Employee’s Account

# Tasks
1. Lock the user account for j.doe to prevent logins.

# Requirements
1. The user account j.doe must be locked.

2. Do not delete the user or their home directory.

# Solution:
`sudo passwd -l j.doe.`
