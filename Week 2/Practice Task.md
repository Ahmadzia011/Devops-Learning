# **Linux File & Process Manipulation - DevOps Practice Tasks**

## **Task 1: File Management & Symbolic Links**

### **Commands Used:**

```bash
ln -s /etc/devops.conf ~/devops.conf
file ~/devops.conf
rm /etc/devops.conf
```

### **Outcome:**

- Created a symbolic link.
- Verified that deleting the original file broke the link.

---

## **Task 2: Advanced File Search & Filtering**

### **Commands Used:**

```bash
find /var/log/app/ -name "*.log"
grep -rn ERROR /var/log/app/*.log
grep -r failed /var/log/app/*.log | wc -l
```

### **Outcome:**

- Found log files in a directory.
- Searched logs for errors and counted occurrences of "failed."

---

## **Task 3: User & Permission Management**

### **Commands Used:**

```bash
adduser ali
groupadd devops-team
usermod -aG devops-team ali
mkdir -p /home/ali/projects/
chown ali:devops-team /home/ali/projects/
chmod 770 /home/ali/projects/
su - ali
touch /home/ali/projects/testfile.txt
ls -l /home/ali/projects/
```

### **Outcome:**

- Created users & groups.
- Set permissions so only specific users can access a directory.

---

## **Task 4: Log Analysis & Filtering**

### **Commands Used:**

```bash
grep -ai "failed password" /var/log/auth.log
grep -c "authentication failure" /var/log/auth.log
grep -ai "failed password" /var/log/auth.log | awk '{print $(NF-3)}' > failed_ips.txt
head -5 failed_ips.txt
```

### **Outcome:**

- Extracted authentication failures.
- Saved failed login IPs to a file.

---


## **Task 6: Backup & Compression**

### **Commands Used:**

```bash
cp -r /etc/dconf/ /home/dconf/
tar -czvf test.tar.gz /home/dconf/
tar -xzvf test.tar.gz
```

### **Outcome:**

- Created and verified backups using tar.

---

## **Task 7: File Permissions Management**

### **Commands Used:**

```bash
mkdir -p /project
touch /project/file1.txt /project/file2.txt /project/secret.conf
chmod 600 /project/file1.txt /project/file2.txt
chmod 400 /project/secret.conf
chmod 700 /project
ls -l /project
```

### **Outcome:**

- Set correct access permissions for files and directories.

---

## **Task 8: Advanced Text Processing**

### **Extract Employees Who Joined Before 2019:**

```bash
awk -F, '{if(NR==1){print $1, $2, $5} else { if($5 < 2019) {print $1, $2, $5}}}' employees.csv
```



## **Final Summary**

- Practiced essential Linux **file, user, process, and text manipulation** tasks.
- Mastered **file permissions, automation, backups, and monitoring.**
- Used **sed, awk, grep, sort, tar, and other essential commands.**


