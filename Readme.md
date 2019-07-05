# ACCOUNT LEVEL DASHBOARD  
Dashboard relying on Incapsula APIs to view settings of all sites of an account in a clear and actionable dashboard.  
Instant view of settings of all sites and account level statistics  
  
The Account level dashboard includes:  
- table with all main settings assessment (Security and Performance) exportable to xls
- Convenient dashboard showing in a clear way the settings status with export to pdf
- Bulk actions to perform security settings changes to several sites at once


# HOW TO: INSTALL THIS ON A PC or MAC (USING DOCKER, recommended way even for beginners)  
0- Download Docker on your mac or PC
1- Build it:  
•	Create a new directory and place the Dockerfile inside the directory that you just created  
•	Run the following command from the directory that hold the Dockerfile  
•	you can replace dashboard:latest to another tag and value(version)  
#docker build –t dashboard:latest .  
* don't forget the " . " in the syntax above
2- Run it:  
- In order to run and use the dashboard you need to perform port mapping between your external available port to the expose port inside the dockerfile (which is 80 in our dockerfile case)  
#docker run –dti -p 8080:80 dashboard:latest  
3- Use it:  
Browse to 127.0.0.1:8080  

# HOW TO: INSTALL LOCALLY ON A PC using Xampp (some issues reported)
1- download Xampp tool and check that Apache is started on it  
2- copy this code in C:\xampp\htdocs folder on another htdocs subfolder  
3- Browse to localhost\subdomainNameYouGave  
You should see the dashboard !  

# HOW TO: INSTALL THIS ON A LINUX MACHINE  
Using CentOS (commands may vary slightly on other distributions):  
1	cd to your apache document directory, typically /var/www/html/  
	cd /var/www/html/  
2	Install git, if you do not have it installed:  
	yum install git  
3	git clone https://github.com/imperva/account-level-dashboard.git  
4	chown +r apache:apache ./account-level-dashboard  (use the user and group from your web server config file)  


# RUNNING THE DASHBOARD  
Enter the Account Admin APIs (stats could be missing with other API permissions)  
CARE:
if you get an error after running the dashboard on an account with many sites (>50), try to select 7-days  
  
Login Page with API keys  
![alt text](https://raw.githubusercontent.com/imperva/account-level-dashboard/master/images/screenshots/login.png)  
  
Main Dashboard Page  
![alt text](https://github.com/imperva/account-level-dashboard/raw/master/images/screenshots/main%20screen.png)  
  
Security Settings table, per site, exportable in pdf and excel  
![alt text](https://github.com/imperva/account-level-dashboard/raw/master/images/screenshots/security%20assessment%20table.png)  

Bulk Actions Changes to multiple sites at once

ERRORS
If you are getting an error that says "Issue with the API Key or Account Permission", make sure that:
1- The API is properly running on Incapsula API explorer page to confirm it is not a permissions issue
2- Check that you have the curl-ca-bundle.crt file in your C:\xampp\apache\bin if you are using Xampp.  (grab from https://github.com/bagder/ca-bundle if you don't have it and use the right name)

CONTRIBUTIONS  
- reach out to me for suggestion or if you want to contribute: jonathan.gruber@imperva.com  
- You can create your own branch and ping me to suggest merges to the master branch
