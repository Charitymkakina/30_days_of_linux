# Linux User Creation

# Create a new user
`sudo adduser <username>`

This creates a new user, automatically creates a home directory, and Prompts to set a password and user details.

# Add user to sudo group
`sudo usermod-aG sudo username`

`-aG` Appends user to a group

`sudo` group with admin privileges

# Alternative User Creation Method

`sudo useradd -m -s /bin/bash <username> `

meaning: `-m` creates a home directory, and `-s /bin/bash` defines the path to the user's default login shell.

# set or change password
`sudo passwd username` 
Prompts for the admin password first, then asks for the password twice

# Delete a user
`sudo deluser username`

# Remove user and home directory

 `sudo deluser`

  The command removes the home username (it deletes everything).

# View all users
`cat/etc/passwd`

# Extract only username
`cut-d: f1 /etc/passwd`
              
is used in Unix/Linux systems to extract and display a list of all usernames from the `/etc/passwd file.` 
