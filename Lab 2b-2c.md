## SYSTEM MONITORING
Contents 
1. Using netstat and nmap
2. Packet sniffing : tcpdump and Wireshark
3. System Logging
4. Remote Logging
5. Resolving IP addresses in Apache logs
6. Webalizer for Apache
7. Swatchdog
8. Finding files based on specific criteria
9. List open files (lsof)
10. Using AIDE
11. Getting usage statistics
12. Setting Process Limits
13. Process Accounting

## Using netstat and map
- Logged in on (server or client, pick 1)

## Packet sniffers with tcpdump and Wireshark
On any machine:

4. Run tcpdump to capture packets (replace eno16777736 with your network interface).

tcpdump –i eno16777736

5. Ping your other system and observe the captured packets.

6. Browse to a website and observe the captured packets.

7. Use Control-C to stop tcpdump.

8. Run “tcpdump icmp -i eno16777736” to view only ICMP packets. Ping to another system.

9. Run “tcpdump tcp -i eno16777736” to view only TCP packets. Browse to another website.

10. View the man page for tcpdump.

11. Try to start a tcpdump packet capture for 2000 packets and store the raw captured data in a file.

Command: _________________________________________________.

Optional Task

Install Wireshark and Wireshark GUI on one of your systems and try running it.

yum install wireshark wireshark-gnome



3. System Logging


Currently all authpriv messages are logged to /var/log/secure.


On client:

12. In a Virtual Terminal, perform a failed login.

13. Check the contents of /var/log/secure to see the log entry for the failed login .

14. Edit /etc/rsyslog.conf to add the following line in bold under the authpriv line. This means authpriv messages with priority warning and higher will also be logged to the file /var/log/securewarning.

authpriv.* /var/log/secure

authpriv.warning /var/log/securewarning

15. Restart the rsyslog service.

16. Use the logger command to create a logged entry.

logger -p authpriv.warning "This is a test warning"

logger -p authpriv.alert "This is a test alert"

logger -p authpriv.info "This is a test info msg"

17. Check the contents of /var/log/secure and /var/log/securewarning to see which messages are logged to which file.


4. Remote logging

You are going to configure your client (Application Server) to send log messages to your server (Remote Logging Server) using the UDP protocol.


On server:

18. Edit /etc/rsyslog.conf and remove the comment signs from the following lines. From these two lines, which port number will the rsyslog daemon be running on?

$ModLoad imudp

$UDPServerRun 514

19. Restart the rsyslog daemon.

20. Use the netstat command to confirm the port the rsyslog daemon is listening on.

21. Adjust the firewall to allow incoming connections to the rsyslog port.


On client:

22. Edit /etc/rsyslog.conf and change the line you added previously, replacing serverIP with the IP address of your server.

authpriv.warning @serverIP

23. Restart the rsyslog daemon

24. Run logger –p authpriv.warning “This is test warning 2”

25. Check /var/log/secure on both images. The warning message should appear on both images.

5. Resolving IP addresses in Apache Logs


Apache normally records the IP addresses of clients requesting for web pages. The logresolve program can help do a hostname lookup for the IP addresses in Apache logfiles.


On server:

26. Look for the Apache access log files.

ls /var/log/httpd

27. Use the logresolve command to resolve the IP addresses contained in the log file. Store the output into a file

logresolve < /var/log/httpd/<site_access_log> > /tmp/apachelog

28. View the output file. The hostnames of the clients who have accessed your Apache Server should be listed*.

* Since your httpd has setup multiple virtual hosts. The <site_access_log> should be replaced with some file names such as : ssl_access_log, fruits_access_log … etc.

In order to resolve the IP addresses to the hostname, you also need to cater for the hosts file entries defined in /etc/hosts.



6. Webalizer for Apache


On server:

29. Webalizer required the GeoIP packages to be installed first.

yum install GeoIP

30. You may install webalizer using yum

yum install webalizer

Or

Download the webalizer rpm file from BlackBoard and install it.

rpm –ihv --nodeps webalizer-2.23_08-1.el7.nux.x86_64.rpm

31. View the config file /etc/webalizer.conf. Look for the output directory where the analysed output will be stored. (ie. Look for the 'OutputDir' setting.)

32. Check that the Apache web server is running. If it is not running, start it.

33. Visit your Apache website to create at least one page visit for today.

http://localhostsy

34. Run the webalizer for the first time:

webalizer

35. Look at the contents of the output directory (e.g. /var/www/usage).

ls /var/www/usage

36. Restart the Apache web server. View the analysis in a Web Browser. The statistics will be more meaningful for a real website!

http://localhost/usage



7. Swatchdog for real-time Log Monitoring


On server:


37. Install the software dependencies that Swatchdog requires.

yum install perl-ExtUtils-MakeMaker

yum install perl-Time-HiRes

yum install perl-Date-Calc

yum install perl-Date-Manip

yum install perl-TimeDate

38. Download the perl-File-Tail rpm file from BlackBoard and install it.

rpm –ihv perl-File-Tail-0.99_3-21.el7.noarch.rpm


(you may use yum install too).


39. Download the swatchdog tarball from sourceforge.net/projects/swatch/files/swatchdog. A copy is also available on BlackBoard.

40. Unzip the swatchdog tarball.

tar –xvf swatchdog-3.2.4.tar.gz


41. Change directory to the swatchdog directory.

cd swatchdog-3.2.4

42. View the README and INSTALL files to look for the installation instructions.






43. To install Swatchdog, follow the installation instructions. There may be some warnings about missing “tools/reswatchdog” or “tools/swatchdog_oldrc2newrc”, you can ignore them.

perl Makefile.PL

make

make test

make install

make realclean

44. View the man page for swatchdog.

man swatchdog


We will use Swatchdog to monitor the /var/log/secure logfile and to display a message (in bold) on the console whenever anyone tries to do a SSH connection.

45. Create a new file /etc/swatchdog.conf and enter the following lines in it :

watchfor /ssh/

echo bold

46. Run Swatchdog to monitor the /var/log/secure file.

swatchdog –c /etc/swatchdog.conf –t /var/log/secure


On client:

47. Try to SSH to the server.


On server:

48. You will see the messages like those below to alert you of the SSH connection from your client.


49. Press Control-C to stop Swatchdog.


We will use Swatchdog to monitor the /var/log/secure logfile for any failed SSH connection. The alert will be displayed on the console (in red) and emailed to the root user.


50. Edit the file /etc/swatchdog.conf so that it has the following lines :

watchfor /ssh.*(F|f)ailed/

echo bold red

mail addresses=root,subject=”SSH failed connection”

51. Run Swatchdog to monitor the /var/log/secure file.

swatchdog –c /etc/swatchdog.conf –t /var/log/secure


On client:

52. Try to SSH to the server with a wrong username or password.


On server:

53. You should see the message to alert you of the failed SSH connection from your client.

54. Read root’s emails to check that the alert from Swatchdog was emailed successfully.

mail

55. Stop Swatchdog.


We will use Swatchdog to monitor the /var/log/secure logfile for failed SSH connections that occur 6 times within 20 seconds, as this could indicate a possible brute force attack.


56. Edit the file /etc/swatchdog.conf so that it has the following lines :

watchfor /ssh.*[F|f]ailed/

echo bold red

mail addresses=root,subject=”Possible SSH Brute Force Attack”

threshold track_by=$1, type=threshold, count=6, seconds=20

57. Run Swatchdog to monitor the /var/log/secure file.

swatchdog –c /etc/swatchdog.conf –t /var/log/secure


On client:

58. Try to SSH to the server with a wrong username or password 6 times within 20 seconds.


On server:

59. Check the alerts in the terminal and in the emails.

Open another terminal and type in:

mail

60. Stop Swatchdog.


The threshold limit and frequency can be adjusted to detect automated login attempts trying to brute force.


On server:

61. Start swatchdog to run in the background and stay running even the terminal is closed.


nohup swatchdog –c /etc/swatchdog.conf –t /var/log/secure 2>&1 > /dev/null &


62. Close the current terminal. Log out from the root account.


On client:

63. Try to SSH to the server with a wrong dusername or password 6 times within 20 seconds.


On server:

64. Login as root. Open a new terminal. Check the alerts in the emails. Verify the alert(s) is/are correctly generated.

65. Find and terminate the background running swatchdog process

The following will find the process id :

ps –ef | grep swatchdog | grep –v grep

The following will terminate the process with the id found:

kill –SIGKILL <process id>


When combine ps , grep , awk , xargs and kill, you can do the above in one command:


ps -ef | grep swatchdog.conf | grep -v grep | awk '{print $2}' | xargs kill -SIGKILL





8. Finding files based on specific criteria


On any machine:

66. Create a directory /root/permissions

67. Create the following files with the corresponding file permissions in /root/permissions

-rw-r--r-- a (chmod 644 a)

-rw-rw-r-- b (chmod 664 b)

-rw-rw-rw- c (chmod 666 c)

-rw-r--rw- d (chmod 646 d)

-rwxrwxrw- e (chmod 776 e)

68. Try the following find commands

find . –perm 644 (Ans : a)

find . –perm -644 (Ans : a,b,c,d,e)

find . –perm 022 (Ans : none)

find . –perm -022 (Ans : c,e)

find . –perm /022 (Ans : b,c,d,e)

69. Search for files that belong to no user (ie. The user ids associated with the files do not exist)

find / -nouser

70. Search for files that have been modified in the last day

find / -mtime -1

71. Search for files that have been modified in the last hour

find / -mmin -60

72. Look at the man pages for find for other search options.



9. Listing open files (lsof)


On any machine:

73. Use the vi editor to open a text file.

vi /tmp/practice

74. Use lsof to list opened files in the /tmp directory. Is /tmp/practice among them?

lsof +D /tmp

75. List files opened by network-related processes

lsof –n –i

(-n option just to inhibit the conversion of network numbers to name)

76. List files opened by ipv4 network-related processes

lsof –n –i 4


77. List files opened by the process (with process id of <PID>) using –p option


HTTPD_PID=`ps -ef | grep httpd | head -1 | awk '{print $2}'`

lsof –p $HTTPD_PID




10. Using AIDE (Advanced Intrusion Detection Environment)

(A file integrity checking software for intrusion detection.)



On any machine:

78. Install the AIDE package.

yum install aide

79. Look at the AIDE config file /etc/aide.conf to see what will be monitored. For this practical, we will just scan the /root directory. Locate the following section and add the hash sign to comment out the directories except for /root.

# Next decide what directories/files you want in the database

#/boot NORMAL

#/bin NORMAL

#/sbin NORMAL

#/lib NORMAL

#/lib64 NORMAL

#/opt NORMAL

#/usr NORMAL

/root NORMAL

Or you may find the following in a newer version of aide:


In this case, the checking configurations for individual folder are more complex: There are other options other than NORMAL. You can find out the definition of NORMAL, CONTENT_EX and PERMS ..etc in the aide.conf file.


80. Create the first baseline database. The process may take five minutes or longer.

aide –-init -–config /etc/aide.conf

81. The baseline database is created at /var/lib/aide/aide.db.new.gz. In order to use it, it must be renamed as /var/lib/aide/aide.db.gz.

mv /var/lib/aide/aide.db.new.gz /var/lib/aide/aide.db.gz

82. Make a change in the /root directory. For example, create a new file

touch /root/file1

chmod 0666 /root/.bashrc

83. Run a check and compare with the baseline database. The new file that you created, and

the file permission you have changed should be flagged out along with some other changes the AIDE has detected.

aide –-check –-config /etc/aide.conf



11. Getting usage statistics


On any machine:


84. Run the df command to get the disk space utilization.

df -T

df -Th

85. Run the du command to see how big each user’s home directory is.

du –sh /home/*


86. Run the iostat command to see the CPU and disk utilizations.

iostat

iostat –N (to view Logical volume disk utilization)

iostat –m (to view in megabytes instead of kilobytes)

87. Use the free and vmstat commands to see virtual memory statistics

free -m

vmstat

vmstat -s


88. Run the sar command to see a summary of CPU activity.

sar


89. Use the sar command to view available reports and see a report of CPU activity of a previous day. The log files are created on a daily basis, with the filename corresponding to the date.

ls –l /var/log/sa

sar –f /var/log/sa/filename | less


90. Use the sar command to view network statistics on each network interface.

sar –n DEV



12. Settings process limits


On server:

91. Edit the file /etc/security/limits.conf. Append the following line to restrict user alvin to only one login.

alvin hard maxlogins 1

92. Open a Virtual Terminal and login as user alvin. Open another Virtual Terminal and try to login as user alvin again. The second login should not be successful.

93. Remove the line you just added to /etc/security/limits.conf.

94. Type “man limits.conf” to see the various possible configurations.



On server:

95. Open a Virtual Terminal and login as user alvin. Create the following shell script in alvin’s home directory that sleeps for 10 minutes. You can give any filename to your shell script.

#!/bin/bash

sleep 600

96. Make the file executable.

97. Run the sleep script as a background job

./sleep.sh &

98. Repeat the above command five more times.


99. Return to the GUI. As user root, run the ps command to see how many processes that has been started by alvin.

ps –u alvin


100. As user root, kill all the sleep processes.

101. Edit the file /etc/security/limits.conf. Append the following line to restrict user alvin to ten (soft) and twenty (hard) processes.

alvin soft nproc 10

alvin hard nproc 20


102. In the Virtual Terminal, logoff and login again as user alvin.

103. As user alvin, run the following command to see the number of max user processes.

ulimit -a

104. As user alvin, run the sleep script in background mode. Repeat the command until you get an error.


105. Return to the GUI. As user root, run the ps command to see how many processes that has been started by alvin. There should not be more than 10 processes owned by alvin.

ps –u alvin


106. In the Virtual Terminal, as user alvin, run the following command to increase the number of max user processes.

ulimit –u 16

107. As user alvin, run the following command to see the new number of max user processes.

ulimit -a

108. As user alvin, run the sleep script in background mode. You should be able to start a few more sleep processes before you get the error again.

109. Return to the GUI. As user root, kill the sleep processes.

110. As user alvin, run the following command to increase the number of max user processes to above 20. You should not be successful.

ulimit –u 30

111. Type “man limits.conf” to see the various possible configurations.



13. Process Accounting


On server:

112. Install the psacct package (if not yet installed).

yum install psacct

113. Start the psacct service.

114. View the man page for the ac command.

man ac

115. Use the ac command to check the daily connect times for each user.

ac -dp

116. View the man page for the lastcomm command.

man lastcomm

117. Su as user alvin and create a textfile (any filename). Log off as alvin.

118. Use the lastcomm command to view information about the most recent commands run by user alvin.

lastcomm alvin



End of Practical
