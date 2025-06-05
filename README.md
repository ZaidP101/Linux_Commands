# 🐧 Basic Linux Command Reference Guide

A beginner-friendly guide to essential Linux commands, file system navigation, process management, Git usage, Vim basics, and network utilities.

---

## 📁 1. File and Directory Management

```bash
ls                  # Lists files and directories
pwd                 # Prints current working directory
cd                  # Change directory
cd ..               # Move to parent directory
mkdir xyz           # Create directory named xyz
cd xyz              # Navigate to xyz
mkdir abc           # Create directory abc inside xyz
rmdir abc           # Delete directory abc
touch xyz           # Create an empty file named xyz
touch .xyz          # Create a hidden file named .xyz
ls -a               # Show all files including hidden ones
ls -R               # List directory and subdirectories
ls -l               # Show permissions of files/directories
mv file1 folder1/   # Move file1 to folder1
cp file1 folder1/   # Copy file1 to folder1
history             # Show command history
printf "xyz"        # Print text without newline
printf "xyz\n"      # Print text with newline
chmod 123 xyz       # Change file permissions (use calculator)
top                 # Show resource usage
df                  # Show storage details
df -h               # Show human-readable storage info
ps                  # Show running processes
ps -a               # Show background processes
kill 123            # Kill process with PID 123
nohup xyz           # Run command and store output in file
apt install xyz     # Install package from repository
apt-get install xyz # Install package from internet
sudo apt remove xyz # Remove installed package


su root             # Switch to root
sudo visudo         # Open sudoers file
# Add: your_username ALL=(ALL:ALL) ALL
# Save with: Ctrl+Enter, Enter, Ctrl+X


wget <link>                 # Download browser/app
cd Downloads                # Go to downloads folder
sudo dpkg -i <filename.deb> # Install downloaded app

## Git Setup
apt install git
git config --global user.name "Your Name"
git config --global user.email "your@email.com"


## Basic Git Commands
cd <project-folder>
git init                            # Initialize Git repo
git status                          # Check repo status
git add xyz                         # Stage file xyz
git add .                           # Stage all changes
git commit -m "message"             # Commit with message
git remote add origin <repo-link>  # Add remote repo
git push -u origin main             # Push to main branch

sudo apt-get -y install vim
vim xyz                            # Open/create xyz file

## VIM Editor
sudo apt-get -y install vim
vim xyz                            # Open/create xyz file
i: Insert mode
Esc: Exit insert mode
:wq: Save and quit
:q: Qui
:e!: Discard all changes
/abc: Search for 'abc'
:%s/old/new/g: Replace all
u: Undo
Ctrl + r: Redo
dd: Delete line
r: Replace character
y: Copy
p: Paste


## User and Group Management
uname                 # OS platform
uptime                # System uptime
date                  # Show current date
whoami                # Current user
who                   # Logged in users
which xyz             # Path of command xyz
id                    # User and group ID

useradd -m xyz        # Add user xyz
sudo passwd xyz       # Set user password
userdel xyz           # Delete user
sudo groupadd xyz     # Add group xyz
sudo gpasswd -a abc xyz          # Add user abc to group xyz
sudo gpasswd -M abc1,abc2 xyz    # Add multiple users to group
sudo groupdel xyz     # Delete group
sudo chown abc xyz    # Change ownership of xyz to abc
sudo chgrp xyz abc    # Change group of abc to xyz


## Compression and File Transfer
zip -r abc.zip xyz                        # Compress xyz
unzip abc.zip                             # Extract abc.zip
scp -i "pem file" -r server:/home/ .      # Download from server
scp -i "pem file" xyz server:/home/       # Upload to server
rsync -e "ssh -i pem" -avz xyz server:/home/  # Sync folders


## Network Commands
ping xyz                # Check connection
netstat                 # Network connections
ifconfig                # Network interfaces
traceroute xyz          # Trace path to xyz
tracepath xyz           # Alternative to traceroute
mtr xyz                 # Ping + traceroute
nslookup xyz            # DNS information
telnet xyz 80           # Connect to port 80
telnet xyz 443          # Connect to port 443
dig xyz                 # Detailed DNS info
whois xyz               # Domain registration
curl -X GET http://xyz  # HTTP request
wget xyz                # Download file
watch top               # Repeat 'top' every 2 seconds
nmap -v http://xyz      # Scan host


## AWK, SED, and GREP
awk '{print $1,$4,$7}' xyz.log                     # Print columns
awk '/mumbai/ {print $1,$4,$7}' xyz.log            # Filter by keyword
awk '/mumbai/ {count++} END {print count}' xyz.log # Count occurrences
awk '$2 >= "03:00am" && $2 <= "04:00am" {print $2}' xyz.log

sed -n '/mumbai/p' xyz.log             # Print lines with keyword
sed -n -e '/mumbai/=' xyz.log          # Line numbers with keyword
sed '1,10 s/mumbai/delhi/g' xyz.log    # Replace in range

grep -i -c mumbai xyz.log              # Count case-insensitive
ps | grep xyz                          # Filter processes
ps | grep xyz | awk '{print $2}'       # Extract process IDs


echo zaid | base64 -> output = 3f324f. 
this -> "|" is pipe a(input) | b(output)

echo 3f324f | base64 --decode -> output = zaid
