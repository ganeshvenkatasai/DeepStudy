
# Linux Commands Cheat Sheet

## File and Directory Management
- `ls` - List directory contents
- `pwd` - Print working directory
- `cd <dir>` - Change directory
- `mkdir <dir>` - Create directory
- `rmdir <dir>` - Remove empty directory
- `rm -r <dir>` - Remove directory with contents
- `touch <file>` - Create empty file
- `cp <src> <dest>` - Copy files/directories
- `mv <src> <dest>` - Move/rename files
- `rm <file>` - Delete file
- `find <path> -name <pattern>` - Find files by name

## File Viewing
- `cat <file>` - View file contents
- `less <file>` - View file with navigation
- `head <file>` - Show first 10 lines
- `tail <file>` - Show last 10 lines
- `tail -f <file>` - Continuously monitor file

## File Permissions
- `ls -l` - Show file permissions
- `chmod 755 <file>` - Change permissions
- `chown user:group <file>` - Change file ownership

## File Compression & Archiving
- `tar -cvf archive.tar file` - Create tar archive
- `tar -xvf archive.tar` - Extract tar archive
- `gzip file` - Compress with gzip
- `gunzip file.gz` - Decompress gzip file
- `zip archive.zip file` - Create zip file
- `unzip archive.zip` - Extract zip file

## Process Management
- `ps` - Show running processes
- `ps aux` - Show all processes
- `top` - Real-time process monitoring
- `htop` - Interactive process viewer
- `kill <pid>` - Kill process by PID
- `killall <name>` - Kill process by name

## User Management
- `whoami` - Current user
- `id` - User ID and group ID
- `adduser <user>` - Add user
- `passwd <user>` - Change password
- `su <user>` - Switch user
- `sudo <command>` - Run command as root

## Networking
- `ifconfig` - Show network interfaces
- `ip addr` - Show IP addresses
- `ping <host>` - Test connectivity
- `curl <url>` - Fetch from URL
- `wget <url>` - Download file
- `scp <src> <user>@<host>:<dest>` - Secure copy
- `ssh <user>@<host>` - SSH login
- `netstat -tulnp` - Show open ports
- `ss -tuln` - Show socket statistics

## Disk Management
- `df -h` - Show disk usage
- `du -sh <dir>` - Show directory size
- `mount <device> <dir>` - Mount device
- `umount <device>` - Unmount device

## Package Management (Debian/Ubuntu)
- `apt update` - Update package list
- `apt upgrade` - Upgrade packages
- `apt install <pkg>` - Install package
- `apt remove <pkg>` - Remove package

## Package Management (RHEL/CentOS)
- `yum install <pkg>` - Install package
- `yum remove <pkg>` - Remove package
- `yum update` - Update system

## System Information
- `uname -a` - Show system info
- `hostname` - Show hostname
- `uptime` - Show uptime
- `dmesg` - Kernel messages
- `free -h` - Show memory usage
- `vmstat` - System performance
- `lscpu` - Show CPU info
- `lsblk` - Show block devices

## Logs
- `journalctl` - Show system logs
- `dmesg` - Show kernel logs
- `tail -f /var/log/syslog` - View live logs

## Search & Text Processing
- `grep <pattern> <file>` - Search text
- `grep -r <pattern> <dir>` - Recursive search
- `awk '{print $1}' <file>` - Process text
- `sed 's/foo/bar/g' <file>` - Replace text
- `sort <file>` - Sort text
- `uniq <file>` - Remove duplicates

## Others
- `history` - Show command history
- `alias ll='ls -l'` - Create alias
- `date` - Show date/time
- `cal` - Show calendar
- `echo "text"` - Print text
- `man <command>` - Show manual
