# profile-html
This is my profile built only using simple html

Download the index.html and images folder form github repo to your httpd server into /var/www/html/
   

For any issues with file permissions refer below: 

Summary of Actions for resolving the issue Permission denied: [client 192.168.0.237:50845] AH00132: file permissions deny server access: /var/www/html/images/profile.png

above IP address may change due to server. 

Set Correct Permissions:

bash
Copy code
sudo chmod 755 /var/www/html/images
sudo chmod 644 /var/www/html/images/profile.png
Ensure Correct Ownership:

bash
Copy code
sudo chown apache:apache /var/www/html/images/profile.png
sudo chown apache:apache /var/www/html/images
Check Apache Configuration: Ensure that the Apache configuration allows access to the /var/www/html/images/ directory.

Check .htaccess File: Remove or adjust any restrictive rules like Deny from all or Require all denied.

Check SELinux: Temporarily disable SELinux if it’s enforcing:

bash
Copy code
sudo setenforce 0
Review Apache Logs:

bash
Copy code
sudo tail -f /var/log/httpd/error_log

