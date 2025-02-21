
# 🐧 Linux Commands Practice Guide  

## 🔹 Introduction to Linux  

Linux is an open-source, Unix-like operating system that provides a powerful command-line interface (CLI) for managing files, processes, users, and system configurations.  


## 🔹 Basic Linux Commands  

### 📂 **File and Directory Management**  

| Command | Description |
|---------|------------|
| `ls` | List files and directories |
| `ls -l` | Detailed list view (permissions, size, owner) |
| `ls -a` | Show hidden files |
| `mkdir <dir>` | Create a new directory |
| `rmdir <dir>` | Remove an empty directory |
| `rm <file>` | Delete a file |
| `rm -r <dir>` | Delete a directory and its contents |
| `mv <source> <destination>` | Move/rename files or directories |
| `cp <source> <destination>` | Copy files |
| `touch <file>` | Create an empty file |

---




## Linux Basic Commands Task I did 

1️⃣ Create a directory Linux_Task with subdirectories docs, scripts, and backup.

2️⃣ Inside docs, create notes.txt, tasks.txt, and log.txt.

3️⃣ Write "Linux command practice" into notes.txt.

4️⃣ Rename tasks.txt to todo.txt.

5️⃣ Move log.txt to backup and copy notes.txt there as notes_backup.txt.

6️⃣ Create an empty run.sh inside scripts and make it executable.

7️⃣ List all files in Linux_Task.

8️⃣ Delete the backup directory.


```sh
mkdir linux_task

cd linux_task/

mkdir docs scripts backup

cd docs/

touch notes.txt task.txt log.txt

mv task.txt todo.txt

mv log.txt /home/ahmad/Downloads/linux_task/backup/

cp notes.txt /home/ahmad/Downloads/linux_task/backup/notes_backup.txt

touch run.sh /home/ahmad/Downloads/linux_task/scripts/

rm -r backup/

