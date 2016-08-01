# Installing BIND 9 DNS Server on CentOS 7

This guide assumes the use of BIND v9.10.4-P2 (the most current version at the time of writing) and CentOS 7 minimal install. Any other versions of software or distributions may have different dependencies, options, or commands.

# Install CentOS 7

1. Start the machine with a CentOS install DVD inserted. Select the CD drive as the boot device if necessary.

2. When the CentOS install DVD boots, select "Install CentOS 7" from the menu using the arrow keys and hit the Enter key.  
![boot menu selection](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-001.png)

3. After the installer loads, make sure that "English (United States)" is selected as the language and click the Continue button.  
![language selection](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-002.png)

4. On the main install screen, click "Network & Host Name"  
![main install screen](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-003.png)

5. Enter the desired hostname in the "Host name" box. If the computer should use DHCP instead of a static IP, skip the next step. If a static IP is needed, click the "Configure" button.  
![network hostname](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-004.png)

6. To configure the static IP, select the "IPv4 Settings" tab, select "Manual" from the drop-down menu, and click the Add button. Enter the desired IP address, netmask (or CIDR mask), and gateway. List the DNS servers to use in the "DNS Servers" box, each one separated by commas. Click the Save button.  
![static ip](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-005.png)

7. Click the On/Off toggle to turn the network interface on. If no static IP was entered, DHCP will be used. Click the Done button.  
![turn on network interface](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-006.png)

8. Back on the main install screen, click "Date & Time".  
![main install screen](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-007.png)

9. Select the appropriate time zone. For US Central time, select "Americas/Chicago". Make sure the the "Network Time" in the upper right is set to "On". Click the Done button.
![date time](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-008.png)

10. Back on the main install screen, click "Installation Destination".
![main install screen](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-009.png)

11. Make sure that "Automatically configure partitioning" is selected. Click the Done button.
![installation destination](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-010.png)

12. Back on the main install screen, click the Begin Installation button.
![main install screen](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-011.png)

13. While the operating system is being installed, click "Root Password".
![during installation](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-012.png)

14. Enter the desired root user password in both boxes. Click the Done button.
![root password](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-013.png)

15. After the install has finished, click the Reboot button.
![install finished](https://github.com/antonc42/cs406-project/blob/master/images/centos-install-014.png)

16. Make sure to remove the install disk from the CD drive

# Prerequisites

