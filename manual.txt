FIRST OF ALL:
1. Bind domain to server IP
2. Wait until it successfully binded (it requires to setup HTTPS connection)

INSTALLATION:

1. Install Docker on linux
2. Install docker compose (if it not installed already)
3. Install Portainer to access docker stacks and containers by WEB UI (https://docs.portainer.io/start/install-ce/server/docker/linux)
4. Open Portainer --> Stacks --> Create new stack

5. Pass into your docker-compose.yml file BUT:
5.1. Change VT_SITE_URL and DOMAINS variables to pass your domain (replace 'domain.com' with your domain)
5.2. Create stack
5.3. Wait until 'https-portal' register your domain with this container

6. Open your 'domain.com' in browser
6.1. Click 'Install'
6.2. Click 'I Agree'
6.3. Click 'Next' then 'OK'

6.4.1. Host Name = mysql
6.4.2. User Name = root
6.4.3. Password = vtiger
6.4.4. Database Name = vtiger
6.4.5. Click 'Create new database'
6.4.6. Root User Name = root
6.4.7. Root Password = vtiger
6.4.8. Everything else fill like you want
6.4.9. So when you click 'Next' - no errors will appear
6.4.10. Click 'Next'
6.4.11. Everything else fill like you want
6.5. Now you redirect to CRM and see 'Illegal request' error (it's OK)

7. Now open Portainer
7.1. Go to vtiger container
7.2. Click 'Console' to connect inside vtiger container
7.3. You will see something like this:

root@1d71ecf5fbd0:/var/www/html#

7.4. Type 'cd includes'
7.5. Type 'cd http'
7.6. Now we need to edit 'Request.php' file
7.6.1. Type 'apt-get update'
7.6.2. Type 'apt-get install vim'

7.7. Type 'vi Request.php'
7.8. Find 'protected function validateReferer()' method (we need to set return always true)
7.9. Type / followed by the string you want to search for, and then press Return
7.10. To edit file press 'i'
7.11. To save type :wq! (semicolon press with Shift button)

8. Restart stack
9. ??????
10. PROFIT
