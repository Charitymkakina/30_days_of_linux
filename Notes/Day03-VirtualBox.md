# Objective
Install and run an `Ubuntu virtual machine.`

Understand VM configuration and troubleshooting

# Issues Encountered
While I was starting the virtual machine, I experienced:
1. Slow performance
2. Boot issues
3. Desktop environment not loading after the Ubuntu logo

# VM Configuration fix
`RAM` - 4096

`CPUs` - 2

`Network Adapter` - NAT

`Video Memory` - 128MB

Note: Allocating about 50% of the host machine’s resources ensures a balance between VM performance and host system stability.

# Additional Issue
Even after fixing resources:

Ubuntu booted to the logo screen, but the desktop environment failed to load.

ROOT CAUSE: The issue was caused by a conflict between:

1. Hyper-V
2. Windows Isolation Features

These interfere with VirtualBox virtualization.

# Solution
Steps taken to resolve the issue:

1. Disabled Hyper-V and Windows Isolation in Windows Features
2. Restarted the computer
3. Opened PowerShell (Administrator) and executed: `bcdedit /set hypervisorlaunchtype off`
4. Restarted the system again
5. Launched VirtualBox and started the VM

# Outcome
Ubuntu VM booted successfully

Desktop environment loaded properly

System performance stabilized


