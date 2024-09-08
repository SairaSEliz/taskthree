# System Configuration and Network Information

## Steps Performed
1. **Changed Username, Password, and Hostname**

-Change Username: You need to first create a new user with administrative privileges and then delete the old user.

$sudo useradd -m newusername
$sudo usermod -aG sudo newusername
$sudo passwd newusername

-Switch to the New User:

$su - newusername
Remove Old Username (if needed):
$sudo deluser oldusername

-Change Password

$passwd
Enter the new password when prompted.

-Change Hostname

$sudo hostname newhostname
Change Hostname Permanently: Edit the hostname file:


$sudo nano /etc/hostname
Replace the existing hostname with newhostname, then save and exit.

-Edit the hosts file:

$sudo nano /etc/hosts
127.0.0.1   newhostname
Save and exit.

2. **Network Information**
   
-Find Public IP:

$curl ifconfig.me
$ip addr show
Look for the inet field under the relevant network interface (e.g., eth0 or wlan0).

-Find MAC Address:

$ip link show
Look for the link/ether field under the relevant network interface.

3. **Compressed Information**
   
-Create a Text File:
nano info.txt
Add the collected information (public IP, private IP, MAC address) to the file and save it.

-Compress the File with a Password:
zip -e info.zip info.txt
Enter and confirm the password when prompted.
