# System's Security Strengthening with Linux

System strengthening with Linux means making sure your Linux computer or server is secure and running smoothly by protecting it from threats and improving its performance.

## Here’s why it’s important:

- [Security](#Security) - Hackers can try to break into your system, steal data, or cause harm. Strengthening your system means setting up protections like firewalls, updates, and monitoring, so your system is less likely to be compromised.
- [Performance](#Performance) - Over time, your system can slow down or become cluttered. Strengthening it involves optimizing resources (like memory and disk space), so your system runs faster and more efficiently.
- [Data Integrity](#DataIntegrity) - Your files and data are important. Strengthening your system helps ensure they are safe from corruption, unauthorized access, or loss.
- [Preventing Attacks](#PreventingAttacks) - Weak systems can be easy targets for cyberattacks. By strengthening the system, you make it harder for attackers to exploit weaknesses and compromise your system.
- [Maintenance](#Maintenance) - Regular system strengthening (like software updates and cleaning up unnecessary files) helps keep everything up-to-date and running well over the long term.


## 1. Update System Packages
sudo apt update

sudo apt upgrade -y

These commands update your package lists from the repository and upgrade all installed packages to their latest versions. Security patches and updates for software packages are often released regularly, so updating ensures your system is protected against known vulnerabilities.
Keeping your system up-to-date is one of the most important steps in security. Outdated software can have vulnerabilities that could be exploited by attackers.

## 2. Check System Information
uname -a

lsb_release -a

uname -a provides detailed information about the system's kernel and architecture. lsb_release -a gives information about the Linux distribution, version, and codename.
Knowing your system’s details is essential when you need to troubleshoot or apply security patches specific to your Linux version.

## 3. View Active Users
who

w

These commands show who is currently logged into the system. who lists logged-in users, while w provides more detailed information, including the user's activity.
Monitoring active users helps to detect unauthorized access or unexpected logins. If you see an unfamiliar user, it could be a sign of a potential security breach.

## 4. Check Open Ports
sudo netstat -tuln

This command shows all open network ports and their associated services. It lists listening ports (for both TCP and UDP), which is important for understanding which services are accessible over the network.
Open ports can be an entry point for attackers. It's important to regularly check and ensure only trusted services are open.

## 5. List Installed Packages
dpkg --get-selections

This command lists all installed packages on a Debian-based system (e.g., Ubuntu). It's useful for auditing installed software.
Ensuring that only trusted software is installed can help prevent malicious programs from running. Unnecessary or unknown packages should be removed.

## 6. Check for Failed Login Attempts
sudo grep "Failed password" /var/log/auth.log

This command searches the authentication log for failed login attempts. Multiple failed logins can indicate brute-force attacks or attempts to gain unauthorized access.
Detecting failed login attempts allows you to identify potential attackers and take action, such as blocking IPs or improving authentication methods.

## 7. Set Up a Firewall (UFW)
sudo ufw enable

sudo ufw allow ssh

sudo ufw status

UFW (Uncomplicated Firewall) is used to manage firewall rules. The first command enables the firewall, the second allows SSH traffic (so you can access the system remotely), and the third shows the firewall status.
A firewall helps protect the system from unauthorized access and attacks. It ensures that only authorized traffic can reach your system.

## 8. Monitor Disk Usage
df -h

du -sh *

df -h shows disk space usage for mounted filesystems, while du -sh * shows the disk usage of files and directories in the current directory.
Unusual disk space consumption can be a sign of a malware infection or other suspicious activity, such as unauthorized file creation or data exfiltration.

## 9. Check Running Processes
ps aux

top

ps aux shows all running processes, while top provides a dynamic, real-time view of active processes.
Monitoring running processes allows you to detect suspicious or unexpected activity. If malicious software is running, it will often appear as an unusual process.

## 10. User Management Commands
sudo useradd <username>

sudo passwd <username>

sudo userdel <username>

These commands allow you to add new users, set or change their passwords, and delete users from the system.
Proper user management ensures that only authorized individuals have access to your system. Removing unused or unauthorized accounts reduces the attack surface.

## 11. Verify File Integrity (AIDE)
sudo aide --check

AIDE (Advanced Intrusion Detection Environment) checks the integrity of system files. It helps detect changes in important system files that could indicate a breach.
AIDE can alert you to unauthorized changes to system files, which may be the result of a security breach or malware activity.

## 12. View System Logs
sudo less /var/log/syslog

sudo less /var/log/auth.log

These commands allow you to view system logs that contain records of system activity and authentication events.
Logs are essential for identifying security-related events, such as system errors, unauthorized access attempts, or unusual behavior. Regularly checking logs helps detect potential security incidents.



