# Installing BIND 9 DNS Server on CentOS 7

This guide assumes the use of BIND v9.10.4-P2 (the most current version at the time of writing) and CentOS 7 minimal install. Any other versions of software or distributions may have different dependencies, options, or commands.

# Install CentOS 7

1. Start the machine with a CentOS install DVD inserted. Select the CD drive as the boot device if necessary.

2. When the CentOS install DVD boots, select "Install CentOS 7" from the menu using the arrow keys and hit the Enter key.  
![boot menu selection](images/centos-install-001.png)

 <div class="page-break"></div>

3. After the installer loads, make sure that "English (United States)" is selected as the language and click the Continue button.  
![language selection](images/centos-install-002.png)

 <div class="page-break"></div>

4. On the main install screen, click "Network & Host Name"  
![main install screen](images/centos-install-003.png)

 <div class="page-break"></div>

5. Enter the desired hostname in the "Host name" box. If the computer should use DHCP instead of a static IP, skip the next step. If a static IP is needed, click the "Configure" button.  
![network hostname](images/centos-install-004.png)

 <div class="page-break"></div>

6. To configure the static IP, select the "IPv4 Settings" tab, select "Manual" from the drop-down menu, and click the Add button. Enter the desired IP address, netmask (or CIDR mask), and gateway. List the DNS servers to use in the "DNS Servers" box, each one separated by commas. Click the Save button.  
![static ip](images/centos-install-005.png)

 <div class="page-break"></div>

7. Click the On/Off toggle to turn the network interface on. If no static IP was entered, DHCP will be used. Click the Done button.  
![turn on network interface](images/centos-install-006.png)

 <div class="page-break"></div>

8. Back on the main install screen, click "Date & Time".  
![main install screen](images/centos-install-007.png)

 <div class="page-break"></div>

9. Select the appropriate time zone. For US Central time, select "Americas/Chicago". Make sure the the "Network Time" in the upper right is set to "On". Click the Done button.
![date time](images/centos-install-008.png)

 <div class="page-break"></div>

10. Back on the main install screen, click "Installation Destination".
![main install screen](images/centos-install-009.png)

 <div class="page-break"></div>

11. Make sure that "Automatically configure partitioning" is selected. Click the Done button.
![installation destination](images/centos-install-010.png)

 <div class="page-break"></div>

12. Back on the main install screen, click the Begin Installation button.
![main install screen](images/centos-install-011.png)

 <div class="page-break"></div>

13. While the operating system is being installed, click "Root Password".
![during installation](images/centos-install-012.png)

 <div class="page-break"></div>

14. Enter the desired root user password in both boxes. Click the Done button.
![root password](images/centos-install-013.png)

 <div class="page-break"></div>

15. After the install has finished, click the Reboot button.
![install finished](images/centos-install-014.png)

16. Make sure to remove the install disk from the CD drive

<div class="page-break"></div>

# Prerequisites

**Note that some of these dependencies are for the BIND application and others are useful utilities to aid in setup and not strictly dependencies.**

1. Once the system has restarted to the login prompt, login with the username `root` and the password that was set during the install.

2. Install dependencies.
 ```
yum install screen vim bind-utils wget gcc automake net-tools checkpolicy policycoreutils-python perl-Net-DNS-Nameserver perl-IO-Socket-INET6
 ```

3. Add a non-root user, set the password, and allow the user to run commands via `sudo`. Replace **username** with the desired username.
 ```
useradd username
passwd username
echo "username ALL=(ALL) ALL" >> /etc/sudoers
 ```

4.
