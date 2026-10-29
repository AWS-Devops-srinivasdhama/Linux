# Linux Commands for DevOps – Complete Notes

## 1. Basic Linux Commands

### 1. `clear`
**Syntax**
```bash
clear
```
**Real-time use case:** Clear the terminal screen before running commands.

### 2. `pwd`
**Syntax**
```bash
pwd
```
**Real-time use case:** Check your current working directory.

### 3. `uname`
**Syntax**
```bash
uname
uname -a
uname -r
```
**Real-time use case:** Check Linux system information and kernel version.

### 4. `whoami`
**Syntax**
```bash
whoami
```
**Real-time use case:** Identify the current effective user.

### 5. `history`
**Syntax**
```bash
history
history 10
```
**Real-time use case:** Review previously executed commands.

### 6. `history -d`
**Syntax**
```bash
history -d 5
```
**Real-time use case:** Delete entry number 5 from the current shell's history list.

### 7. History shortcuts
**Syntax**
```bash
!!
!5
!ls
```
**Real-time use case:**
- `!!` — execute the previous command again.
- `!5` — execute history entry number 5.
- `!ls` — execute the most recent command beginning with `ls`.

**Caution:** These shortcuts execute commands directly. Review commands carefully before repeating potentially destructive operations.

### 8. `history -c`
**Syntax**
```bash
history -c
```
**Real-time use case:** Clear the current shell's in-memory history list. This does not guarantee removal of saved history files or other records.

### 9. `sudo su`
**Syntax**
```bash
sudo su
```
**Real-time use case:** Open a root shell using sudo.

### 10. `sudo su -`
**Syntax**
```bash
sudo su -
```
**Real-time use case:** Open a root login shell with root's login environment.

---

## 2. Files and Directories

### 11. `ls`
**Syntax**
```bash
ls
ls -l
ls -la
ls -lh
ls -lrth
ls -lrtha
ls -li
ll
```
**Real-time use case:** List files and directories.
- `-l` — detailed listing.
- `-a` — include hidden files.
- `-h` — human-readable sizes.
- `-r` — reverse order.
- `-t` — sort by modification time.
- `-i` — display inode numbers.
- `ll` — commonly an alias for `ls -l`.

**Correction:** Use `ls -li` for inode numbers. `ls -I` is an ignore-pattern option.

### 12. `mkdir`
**Syntax**
```bash
mkdir one
mkdir -p one/two/three
mkdir -v dev
mkdir -m 755 ops
```
**Real-time use case:** Create directories for applications, deployments, and project files.
- `-p` — create parent directories as needed.
- `-v` — display messages about directories created.
- `-m` — set permissions during creation.

**Note:** Avoid `777` permissions unless absolutely necessary.

### 13. `touch`
**Syntax**
```bash
touch devops.txt
```
**Real-time use case:** Create an empty file or update its timestamps.

### 14. `cd`
**Syntax**
```bash
cd ..
cd ../..
cd ~
cd -
```
**Real-time use case:** Navigate between directories.
- `cd ..` — parent directory.
- `cd ../..` — two levels up.
- `cd ~` — home directory.
- `cd -` — previous directory.

### 15. `cp`
**Syntax**
```bash
cp file.txt backup.txt
cp -r project/ project_backup/
```
**Real-time use case:** Copy files and directories for backups or testing.

### 16. `mv`
**Syntax**
```bash
mv old.txt new.txt
mv file.txt /tmp/
```
**Real-time use case:** Rename files or move them to another directory.

### 17. `rm`
**Syntax**
```bash
rm dev.txt
rm -r dev/
rm -rf dev/
```
**Real-time use case:** Delete files or directories.

**Caution:** `rm -rf` recursively forces removal. Always verify the target path before running it.

### 18. `rmdir`
**Syntax**
```bash
rmdir dev/
```
**Real-time use case:** Remove an empty directory.

### 19. `stat`
**Syntax**
```bash
stat file.txt
```
**Real-time use case:** Inspect file size, permissions, inode, and timestamps.

### 20. `file`
**Syntax**
```bash
file demo.txt
```
**Real-time use case:** Identify a file's actual type.

### 21. `basename`
**Syntax**
```bash
basename /var/log/app.log
```
**Real-time use case:** Extract `app.log` from a file path in a shell script.

### 22. `dirname`
**Syntax**
```bash
dirname /var/log/app.log
```
**Real-time use case:** Extract `/var/log` from a file path.

---

## 3. File Editing and Reading

### 23. `vi`
**Syntax**
```bash
vi dev.txt
```
Inside `vi`, press `Esc` before entering these commands:

```vim
:set number
:set nonumber
/data
:34
:wq
:q!
```

**Real-time use case:**
- `:set number` — display line numbers.
- `:set nonumber` — hide line numbers.
- `/data` — search for `data`.
- `:34` — jump to line 34.
- `:wq` — save and exit.
- `:q!` — exit without saving.

### 24. `cat`
**Syntax**
```bash
cat one.txt
cat one.txt two.txt
cat one.txt > two.txt
cat one.txt two.txt >> three.txt
cat -n one.txt
cat *.txt
```
**Real-time use case:** Display file contents or combine files.
- `>` — overwrite the destination.
- `>>` — append to the destination.
- `-n` — number output lines.
- `*.txt` — match text files.

### 25. `tac`
**Syntax**
```bash
tac file.txt
```
**Real-time use case:** Display lines in reverse order.

### 26. `head`
**Syntax**
```bash
head file.txt
head -n 10 file.txt
head -q file1.txt file2.txt
```
**Real-time use case:** Display the first 10 lines by default. `-q` suppresses filename headers for multiple files.

### 27. `tail`
**Syntax**
```bash
tail file.txt
tail -n 10 file.txt
tail -q file1.txt file2.txt
tail -f /var/log/messages
```
**Real-time use case:** Display the last lines of a file or follow new log entries using `-f`.

### 28. Display a specific line range
**Syntax**
```bash
tail -20 dev.txt | head -10
```
**Real-time use case:** Display lines 11–20, provided the file contains at least 20 lines.

### 29. `more` and `less`
**Syntax**
```bash
more file.txt
less file.txt
```
**Real-time use case:** Read large files one screen at a time. `less` supports backward navigation and searching.

### 30. `echo`
**Syntax**
```bash
echo "Hello DevOps"
echo "$HOME"
echo "New line" >> notes.txt
```
**Real-time use case:** Print text, display variables, or append text to a file.

**Caution:** Using `>` instead of `>>` overwrites existing content.

### 31. `printf`
**Syntax**
```bash
printf "Name: %s\n" "Srinu"
printf "Count: %d\n" 5
```
**Real-time use case:** Produce formatted output in shell scripts.

---

## 4. Searching and Text Processing

### 32. `grep`
**Syntax**
```bash
grep "error" dev.txt
grep -i "error" dev.txt
grep -l "error" *.log
grep -c "error" dev.txt
grep -w "error" dev.txt
grep -o "error" dev.txt
grep -n "error" dev.txt
grep -v "error" dev.txt
grep -B 5 "error" dev.txt
grep -A 5 "error" dev.txt
grep -C 5 "error" dev.txt
```
**Real-time use case:** Search application logs and configuration files.
- `-i` — ignore case.
- `-l` — list filenames containing matches.
- `-c` — count matching lines, not every occurrence.
- `-w` — match a whole word.
- `-o` — print only matching text.
- `-n` — display line numbers.
- `-v` — display nonmatching lines.
- `-B 5` — show five lines before a match.
- `-A 5` — show five lines after a match.
- `-C 5` — show context before and after a match.

### 33. `sort`
**Syntax**
```bash
sort file.txt
sort -r file.txt
sort -n numbers.txt
sort -k 2 file.txt
sort -k 3,3 file.txt
sort -u file.txt
```
**Real-time use case:** Sort log entries, names, numbers, or records.
- `-r` — reverse order.
- `-n` — numerical sorting.
- `-k 2` — sort starting at field 2; later fields may affect ordering.
- `-k 3,3` — use only field 3 as the sort key.
- `-u` — output unique lines.

### 34. `uniq`
**Syntax**
```bash
sort names.txt | uniq
sort names.txt | uniq -c
sort names.txt | uniq -d
```
**Real-time use case:** Identify unique or repeated entries in logs and lists.

**Note:** `uniq` normally detects adjacent duplicates, so use `sort` first when necessary.

### 35. `cut`
**Syntax**
```bash
cut -d ':' -f 1 /etc/passwd
cut -d ',' -f 1,3 employees.csv
cut -c 1-5 file.txt
```
**Real-time use case:** Extract selected fields or character ranges. The delimiter must match the file format.

### 36. `tr`
**Syntax**
```bash
tr 'a-z' 'A-Z' < file.txt
tr 'A-Z' 'a-z' < file.txt
tr -d '0-9' < file.txt
```
**Real-time use case:** Change letter case or remove specified characters.

### 37. `wc`
**Syntax**
```bash
wc file.txt
wc -l file.txt
wc -w file.txt
wc -c file.txt
```
**Real-time use case:** Count lines, words, and bytes.

### 38. `awk`
**Syntax**
```bash
awk '{print $1}' employees.txt
awk '{print $1, $3}' employees.txt
awk '$3 > 40000 {print $1, $3}' employees.txt
```
**Real-time use case:** Extract columns or filter records, such as employees earning more than 40,000.

### 39. `sed`
**Syntax**
```bash
sed 's/error/ERROR/' file.txt
sed 's/error/ERROR/g' file.txt
sed -n '1,10p' file.txt
```
**Real-time use case:** Replace text or display selected lines.
- Without `g`, replace the first match on each line.
- With `g`, replace all matches on each line.
- `-n '1,10p'` — display lines 1–10.

**Note:** These examples do not modify the original file in place.

### 40. `diff`
**Syntax**
```bash
diff file1.txt file2.txt
diff -u file1.txt file2.txt
```
**Real-time use case:** Compare configuration files, scripts, or application versions.

### 41. `find`
**Syntax**
```bash
find /home -name "devops.txt"
find /var/log -type f
find /var/log -type f -name "*.log"
find /tmp -type f -mtime +7
```
**Real-time use case:** Locate files by name, type, or modification age.

### 42. `xargs`
**Syntax**
```bash
find . -name "*.tmp" -print0 | xargs -0 -r ls -l
```
**Real-time use case:** Pass filenames from `find` to another command. The `-print0` and `-0` options safely handle filenames containing spaces.

### 43. `tee`
**Syntax**
```bash
command | tee output.txt
command | tee -a output.txt
```
**Real-time use case:** Display command output while saving it to a file. `-a` appends instead of overwriting.

### 44. `tree`
**Syntax**
```bash
tree
tree -L 2
tree /var/www
```
**Real-time use case:** View directory structures in a tree format.

---

## 5. Permissions and Ownership

### 45. `chmod`
**Syntax**
```bash
chmod 644 file.txt
chmod 755 script.sh
chmod ugo+rwx file.txt
chmod -v 644 file.txt
chmod -R 755 directory/
```
**Real-time use case:** Set permissions on application files and directories.

Permission values:
- `r = 4` — read.
- `w = 2` — write.
- `x = 1` — execute or directory traversal.
- `u` — owner, `g` — group, `o` — others, `a` — all.

**Important:** `chmod -R 444 DevOps/` removes execute permission from directories and can prevent access. Avoid it when directories need to remain accessible.

### 46. `umask`
**Syntax**
```bash
umask
umask 0022
umask 0026
```
**Real-time use case:** Control default permissions for newly created files and directories.

| Umask | Typical file permissions | Typical directory permissions |
|---|---|---|
| `0022` | `644` | `755` |
| `0026` | `640` | `751` |

These examples assume normal starting permissions of `666` for files and `777` for directories.

### 47. `chown`
**Syntax**
```bash
sudo chown srinu file.txt
sudo chown srinu:staging file.txt
sudo chown -R srinu:staging dev/
```
**Real-time use case:** Change the owner or owner and group of application files.

### 48. `chgrp`
**Syntax**
```bash
sudo chgrp ec2-user file.txt
sudo chgrp -R staging dev/
```
**Real-time use case:** Change group ownership.

### 49. `getfacl` and `setfacl`
**Syntax**
```bash
getfacl file.txt
setfacl -m u:ec2-user:r file.txt
```
**Real-time use case:** Inspect and configure additional file permissions for specific users. These commands may require the ACL utilities package.

---

## 6. Users and Groups

### 50. `id`
**Syntax**
```bash
id
id ec2-user
```
**Real-time use case:** Check UID, primary group, and supplementary groups.

### 51. `who`
**Syntax**
```bash
who
```
**Real-time use case:** List currently logged-in sessions.

### 52. `w`
**Syntax**
```bash
w
```
**Real-time use case:** Check logged-in users and their current activity.

### 53. `users`
**Syntax**
```bash
users
```
**Real-time use case:** Display usernames currently logged in.

### 54. `groupadd`
**Syntax**
```bash
sudo groupadd dev
```
**Real-time use case:** Create a group for team access.

### 55. `usermod`
**Syntax**
```bash
sudo usermod -aG dev ec2-user
```
**Real-time use case:** Add a user to a supplementary group.

**Important:** Use `-aG` to append the group without replacing existing supplementary groups. A new login session may be required.

### 56. `lid`
**Syntax**
```bash
lid ec2-user
lid -g dev
```
**Real-time use case:** Depending on the installed implementation, list group membership.

**Note:** `lid` is not available by default everywhere. Use these alternatives:
```bash
id ec2-user
getent group dev
```

---

## 7. Processes and System Monitoring

### 57. `ps`
**Syntax**
```bash
ps
ps -a
ps -ef
ps aux
```
**Real-time use case:** Inspect running processes.
- `ps` — processes associated with the current terminal.
- `ps -a` — processes associated with terminals, with some exclusions.
- `ps -ef` — full-format process listing.
- `ps aux` — detailed BSD-style process listing.

### 58. `top`
**Syntax**
```bash
top
```
**Real-time use case:** Monitor CPU, memory, and running processes interactively.

### 59. `uptime`
**Syntax**
```bash
uptime
```
**Real-time use case:** Check uptime, logged-in user count, and load averages.

### 60. `free`
**Syntax**
```bash
free -h
```
**Real-time use case:** Check RAM and swap usage.

### 61. `kill`
**Syntax**
```bash
kill -l
kill PID
kill -9 PID
```
**Real-time use case:** Send a signal to a process.
- `kill PID` — normally requests graceful termination.
- `kill -9 PID` — forces termination.

**Important:** Try normal termination before `kill -9`.

### 62. `lscpu`
**Syntax**
```bash
lscpu
```
**Real-time use case:** Check CPU architecture and core information.

### 63. `lshw`
**Syntax**
```bash
sudo lshw -short
```
**Real-time use case:** Display a summary of hardware devices. Installation may be required.

### 64. `vmstat`
**Syntax**
```bash
vmstat
vmstat 1
```
**Real-time use case:** Monitor system processes, memory, swapping, and CPU activity at one-second intervals.

### 65. `iostat`
**Syntax**
```bash
iostat -xz 1
```
**Real-time use case:** Monitor disk I/O performance and device utilization. Usually requires the `sysstat` package.

---

## 8. Disk and Filesystem Management

### 66. `df`
**Syntax**
```bash
df -h
df -Th
df -i
```
**Real-time use case:** Check filesystem space, filesystem types, and inode availability.

### 67. `du`
**Syntax**
```bash
du -sh /var/log/
du -sh *
du -h --max-depth=1 /var
```
**Real-time use case:** Identify directories consuming disk space.

### 68. `lsblk`
**Syntax**
```bash
lsblk
lsblk -f
```
**Real-time use case:** View block devices, partitions, and filesystem information.

### 69. `mount`
**Syntax**
```bash
mount
findmnt
```
**Real-time use case:** Inspect mounted filesystems and their mount points.

### 70. `blkid`
**Syntax**
```bash
sudo blkid
```
**Real-time use case:** Identify filesystem UUIDs and types, useful when configuring persistent mounts.

---

## 9. Networking and Remote Access

### 71. `hostname`
**Syntax**
```bash
hostname
hostname -I
```
**Real-time use case:** Check the system hostname and assigned IP addresses.

### 72. `ip`
**Syntax**
```bash
ip addr
ip route
ip link
```
**Real-time use case:**
- `ip addr` — inspect network interfaces and addresses.
- `ip route` — inspect routing.
- `ip link` — inspect network interface state.

### 73. `ss`
**Syntax**
```bash
ss -tuln
sudo ss -tulnp
```
**Real-time use case:** Inspect listening TCP/UDP ports. The second command also requests process information where permissions allow.

### 74. `ping`
**Syntax**
```bash
ping -c 4 example.com
```
**Real-time use case:** Test basic network reachability. Some networks block ICMP, so failure does not always mean the server is down.

### 75. `nslookup`
**Syntax**
```bash
nslookup example.com
```
**Real-time use case:** Troubleshoot DNS resolution.

### 76. `dig`
**Syntax**
```bash
dig example.com
dig example.com A
dig example.com MX
```
**Real-time use case:** Inspect DNS records. The `dig` utility may need installation.

### 77. `traceroute`
**Syntax**
```bash
traceroute example.com
```
**Real-time use case:** Investigate the network path to a destination. Installation may be required, and some hops may not respond.

### 78. `curl`
**Syntax**
```bash
curl https://example.com
curl -I https://example.com
curl -o page.html https://example.com
```
**Real-time use case:** Test HTTP endpoints, inspect response headers, or save a response.

### 79. `wget`
**Syntax**
```bash
wget https://example.com/file.zip
wget -O page.html https://example.com
```
**Real-time use case:** Download files from a URL.

### 80. `ssh`
**Syntax**
```bash
ssh ec2-user@SERVER_IP
ssh -i key.pem ec2-user@SERVER_IP
```
**Real-time use case:** Connect securely to a remote Linux server or EC2 instance.

### 81. `scp`
**Syntax**
```bash
scp file.txt ec2-user@SERVER_IP:/tmp/
scp ec2-user@SERVER_IP:/tmp/file.txt .
```
**Real-time use case:** Copy files securely between local and remote servers.

### 82. `rsync`
**Syntax**
```bash
rsync -av project/ /backup/project/
rsync -av file.txt ec2-user@SERVER_IP:/tmp/
```
**Real-time use case:** Synchronize application files or transfer backups efficiently.

**Important:** A trailing slash on `project/` means to copy its contents. Verify paths before using deletion options.

---

## 10. Logs, Date and System Information

### 83. `date`
**Syntax**
```bash
date
date "+%Y-%m-%d %H:%M:%S"
date "+%F %T"
```
**Real-time use case:** Generate timestamps for scripts and log files.

### 84. `timedatectl`
**Syntax**
```bash
timedatectl
timedatectl status
timedatectl list-timezones
```
**Real-time use case:** Check the system clock, timezone, and synchronization status.

### 85. `last`
**Syntax**
```bash
last
last -n 10
```
**Real-time use case:** Review recent login records.

### 86. `journalctl`
**Syntax**
```bash
sudo journalctl -u httpd
sudo journalctl -u httpd -f
sudo journalctl -b
```
**Real-time use case:** Inspect systemd service logs, follow new log entries, or examine logs from the current boot.

### 87. `dmesg`
**Syntax**
```bash
dmesg | tail
sudo dmesg -T | tail
```
**Real-time use case:** Inspect kernel messages related to hardware, drivers, and system errors. Access restrictions may apply.

### 88. `zcat`
**Syntax**
```bash
zcat error.log.gz
```
**Real-time use case:** Read a gzip-compressed log without extracting it.

### 89. `cal`
**Syntax**
```bash
cal
cal 10 2026
```
**Real-time use case:** Display a monthly calendar.

---

## 11. Archive and Compression

### 90. `tar`
**Syntax**
```bash
tar -cvf error.tar error/
tar -xvf error.tar
tar -czvf error.tar.gz error/
tar -xzvf error.tar.gz
tar -tvf error.tar
```
**Real-time use case:** Create, extract, or inspect archives.
- `-c` — create.
- `-x` — extract.
- `-v` — verbose output.
- `-f` — archive filename.
- `-z` — gzip compression.
- `-t` — list archive contents.

### 91. `zip` and `unzip`
**Syntax**
```bash
zip backup.zip file.txt
zip -r project.zip project/
unzip backup.zip
unzip -l backup.zip
```
**Real-time use case:** Compress files or directories and extract ZIP archives.

---

## 12. Shell Utilities and Environment

### 92. `env`
**Syntax**
```bash
env
```
**Real-time use case:** Display environment variables used by applications and shell processes.

### 93. `export`
**Syntax**
```bash
export APP_ENV=dev
echo "$APP_ENV"
```
**Real-time use case:** Set an environment variable that child processes can access.

### 94. `alias`
**Syntax**
```bash
alias ll='ls -l'
alias
```
**Real-time use case:** Create convenient command shortcuts in your shell.

### 95. `type`
**Syntax**
```bash
type ll
type cd
```
**Real-time use case:** Check whether a command is an alias, function, builtin, or executable.

### 96. `command -v`
**Syntax**
```bash
command -v python3
command -v docker
```
**Real-time use case:** Check whether a command can be resolved by the current shell.

### 97. `which`
**Syntax**
```bash
which python3
```
**Real-time use case:** Find the executable path of a command when available.

### 98. `whereis`
**Syntax**
```bash
whereis ls
whereis httpd
```
**Real-time use case:** Locate a command's binary, source, and manual-page files when available.

### 99. `whatis`
**Syntax**
```bash
whatis ls
whatis chmod
```
**Real-time use case:** Display a short manual-page description.

### 100. `man`
**Syntax**
```bash
man ls
man chmod
```
**Real-time use case:** Read detailed command documentation.

### 101. `cal` is covered in the date section.

---

## 13. Services and Package Management

### 102. `systemctl`
**Syntax**
```bash
sudo systemctl status httpd
sudo systemctl start httpd
sudo systemctl stop httpd
sudo systemctl restart httpd
sudo systemctl enable httpd
sudo systemctl enable --now httpd
```
**Real-time use case:** Manage services such as Apache HTTP Server.
- `status` — check service status.
- `start` — start now.
- `stop` — stop now.
- `restart` — restart now.
- `enable` — enable startup at boot.
- `enable --now` — enable at boot and start now.

### 103. `service`
**Syntax**
```bash
sudo service httpd status
sudo service httpd start
sudo service httpd restart
```
**Real-time use case:** Manage services on systems that support the `service` command. Prefer `systemctl` on systemd-based systems.

### 104. `yum` and `dnf`
**Syntax**
```bash
sudo yum install httpd
sudo yum update
sudo dnf install httpd
sudo dnf update
```
**Real-time use case:** Install and update software packages. Use the package manager supported by your distribution.

### 105. `visudo`
**Syntax**
```bash
sudo visudo
```
**Real-time use case:** Safely edit sudoers configuration with syntax validation.

---

## 14. Scheduling and Automation

### 106. `crontab`
**Syntax**
```bash
crontab -e
crontab -l
crontab -r
```
**Real-time use case:**
- `-e` — edit scheduled jobs.
- `-l` — list jobs.
- `-r` — remove the current user's entire crontab.

Cron format:
```text
minute hour day-of-month month day-of-week command
```

Examples:
```cron
*/2 * * * * /usr/bin/touch /home/ec2-user/file.txt
0 2 * * * /usr/bin/rsync -av /home/ec2-user/project/ /backup/project/
```

**Real-time use case:** Run a task every two minutes or synchronize a directory daily at 2:00 AM.

**Caution:** Verify command paths, permissions, and destinations. `crontab -r` deletes all scheduled jobs for that user.

---

## 15. Additional Helpful Commands

### 107. `lsof`
**Syntax**
```bash
sudo lsof -i :80
```
**Real-time use case:** Identify processes using a network port. The `lsof` package may need installation.

### 108. `fuser`
**Syntax**
```bash
sudo fuser -v 80/tcp
```
**Real-time use case:** Identify processes using a file or resource, including a TCP port. Verify the target before using options that terminate processes.

### 109. `free`
Already covered in the system monitoring section.

### 110. `sleep`
**Syntax**
```bash
sleep 5
```
**Real-time use case:** Pause a shell script for five seconds, often between checks or retries.

### 111. `watch`
**Syntax**
```bash
watch -n 5 df -h
```
**Real-time use case:** Re-run a command every five seconds to monitor changing disk usage.

### 112. `timeout`
**Syntax**
```bash
timeout 10s command
```
**Real-time use case:** Limit how long a command is allowed to run. Replace `command` with the actual command and arguments.

### 113. `sha256sum`
**Syntax**
```bash
sha256sum file.tar.gz
```
**Real-time use case:** Calculate a checksum to verify file integrity after downloading or transferring an artifact.

### 114. `diff` is covered in the text-processing section.

---

## 16. Calendar and Hardware Commands

### 115. `lscpu`
**Syntax**
```bash
lscpu
```
**Real-time use case:** Inspect processor architecture and core count.

### 116. `lshw`
**Syntax**
```bash
sudo lshw -short
```
**Real-time use case:** Inspect hardware devices when the utility is installed.

---

## Final corrections to remember

1. Use `ls -li` for inode numbers, not `ll -I`.
2. `grep -c` counts matching lines, not total occurrences.
3. Use `sort -k 2,2` when you want to sort by only the second field.
4. `chmod -R 444` can make directories inaccessible.
5. `umask 0022` typically results in files `644` and directories `755`.
6. `systemctl enable` configures startup at boot; it does not necessarily start the service immediately.
7. `zcat` is for gzip-compressed files.
8. `uniq` normally works on adjacent duplicate lines.
9. `chgrp` accepts a group and a target file or directory.
10. `crontab -r` removes the current user's entire crontab.
11. Commands such as `iostat`, `dig`, `tree`, `lshw`, `lsof`, and `fuser` may require installation.
12. Test destructive commands in your lab environment before using them on production systems.

**Recommended practice order:** Basic commands → files and directories → text processing → permissions and users → processes and monitoring → disk management → networking → services and logs → shell scripting and automation.
