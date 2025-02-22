# Linux Command Tasks & Solutions

## 1. File & File Type
### Tasks:
- Create a directory called `Projects`. Inside it, create 5 files with the following extensions: `.txt`, `.sh`, `.log`, `.conf`, `.py`.
- Determine the type of each file created.
- Display detailed information (size, permissions, inode, etc.) for one of the files.
- Locate all `.log` files in the `/var/log` directory and copy them to a new directory called `LogBackups`.

### My code:
```bash
mkdir Projects
cd Projects
touch file.txt file.sh file.log file.conf file.py
file file.*
find /var/log/*.log
cp /var/log/*.log ~/Downloads/Projects/Log_Backup/
```

---

## 2. Filters
### Tasks:
- Search for the word "error" in all `.log` files in the `/var/log` directory and save the results to `errors.txt`.
- Extract the second column from a CSV file.
- Replace all occurrences of the word "foo" with "bar" in a text file.
- List all unique users from the `/etc/passwd` file.

### My code:
```bash
grep -an error /var/log/*.log > errors.txt
cut -d, -f2 file.csv
sed 's/foo/bar/g' file.txt
cut -d: -f1 /etc/passwd | sort -u
```

---

## 3. Redirection
### Tasks:
- Save the output of listing all files in the `Projects` directory to `directory_listing.txt`.
- Display disk usage and save it to `disk_usage.txt`.
- Save error messages from a command to `error_log.txt` and standard output to `output_log.txt`.

### My code:
```bash
ls -l > directory_listing.txt
df -h > disk_usage.txt
cat test.txt 1> output.txt 2> error_message.txt
```

---

## 4. User & Group Management
### Tasks:
- Create users: `alice`, `bob`, `charlie` and assign them to groups `developers` and `admins`.
- Change the primary group of `alice` to `admins`.
- Set a password for `bob` and lock the account of `charlie`.
- Display the UID, GID, and groups for each user.

### My code:
```bash
useradd bob
useradd alice
useradd charlie
usermod -aG developers,admins bob
usermod -aG developers,admins alice
usermod -aG developers,admins charlie
usermod -g admins alice
passwd bob
usermod -L charlie
id root ahmad charlie bob alice
```

---

## 5. Sudo Privileges
### Tasks:
- Allow `alice` to run only the `apt` command with root privileges.
- Run a command requiring root privileges.
- Configure the system so that `bob` can run `systemctl` without being prompted for a password.

### My code:
```bash
echo "alice ALL=(ALL:ALL) /usr/bin/apt" | sudo tee /etc/sudoers.d/alice
sudo apt install <package_name>
```

---

## 6. Package Management
### Tasks:
- Install and remove `nginx`.
- List all installed packages and save to `installed_packages.txt`.
- Add a new repository and install a package.
- Search for `python3` and display its description.

### My code:
```bash
sudo apt install nginx
sudo apt purge nginx
dpkg -l > ~/Downloads/Projects/installed_packages.txt
dpkg -l | grep "  python3  " | awk '{print "Description: "$5, $6, $7, $8}'
```

---

## 7. Service Management
### Tasks:
- Start and enable `nginx` service.
- Check the status of `sshd` service.
- Stop and restart `sshd` service.

### My code:
```bash
systemctl start nginx
systemctl enable nginx
systemctl status ssh
systemctl stop ssh
systemctl restart ssh
```

---

## 8. Process Management
### Tasks:
- List all running processes and save to `process_list.txt`.
- Identify the most CPU-intensive process and terminate it.
- Run a command in the background and bring it to the foreground.
- Start a process with a lower priority and change its priority.

### My code:
```bash
ps -ef > ~/Downloads/Projects/process_list.txt
top -bn1 -o%CPU | awk -vi=0 '{if(i==7){print $1}; i++}' | xargs kill
```

---

## 9. Archiving & Synchronization
### Tasks:
- Create a compressed archive of the `Projects` directory.
- Extract the archive to `RestoredProjects`.
- Create a compressed archive of `LogBackups` in a different format.
- Synchronize the contents of `Projects` to `ProjectsBackup`.

### My code:
```bash
tar -czvf projects_backup.tar.gz ~/Downloads/Projects/
tar -xzvf ~/Downloads/projects_backup.tar.gz -C ~/Downloads/Restored_Projects/
zip Compressed_Log_Backup.zip Log_Backup/
mkdir Backup_Projects
rsync -r Projects/ Backup_Projects/
```

---

## Bonus Challenge
### Tasks:
- List all users and save to `users.txt`.
- Display disk usage and save to `disk_usage_report.txt`.
- List all running services and save to `services.txt`.
- Combine all reports into a compressed archive.

### My code:
```bash
cut -d: -f1 /etc/passwd > users.txt
df -h > disk_usage_report.txt
ps -ef > services.txt
zip system_report.zip users.txt disk_usage_report.txt services.txt
```

---
