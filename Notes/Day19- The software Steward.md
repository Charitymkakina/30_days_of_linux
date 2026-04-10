# Task
Your mission is to establish order. You'll need to update the system's software sources, 
install essential tools requested by the team, verify that everything is correctly installed, remove obsolete software, 
and perform a general cleanup. This is your opportunity to demonstrate your value and bring professional-grade stability 
and efficiency to the company's infrastructure. The team is counting on you. Let's get this server in shape!

# Solution
1. Update the Software- `sudo apt update.`

2. Inspect the sources- `sudo apt upgrade -y.`
   
3. Full system upgrade- `sudo apt full-upgrade -y.`
   
4. Install essential tools- `sudo apt install curl wget git net-tools htop unzip -y.`
   
5. Verify installation- `dpkg -l | grep curl.`
   
6. Remove obsolete software- `sudo apt remove <package_name>.`
   
7. Remove config files- `sudo apt purge <package_name>.`
   
8. Remove unused dependencies- `sudo apt autoremove -y.`
   
9. Free disk space- `sudo apt clean.`
   
10. Check system health- `df -h.`
    
11. Check running services- `systemctl list-units --type=service --state=running.`

