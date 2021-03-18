# firefly-iii install
This script assumes you are running a flavor of Linux that includes apt package manager.

**DO NOT** run the installer as sudo or root.  Just run `sh installlampwithfirefly.sh`

At the terminal:
  1. `git clone https://github.com/edwardsj9090/firefly-iii-automation`
      NOTE: If you don't have _git_ installed, just run `sudo apt install git`.
  2. `cd firefly-iii-automation`
  3. `sh installlampwithfirefly.sh`

Post-Install (OPTIONAL):

I would recommend changing the firefly mysql connection string defaults in **/var/www/html/firefly-iii/.env** file.

  1.  Change the password for the mysql firefly user.

        Login to your MySQL instance: `sudo mysql -u root -p`
        
        Change the firefly user's password: `ALTER USER 'firefly'@'localhost' IDENTIFIED BY 'newpassword';`
        
  2. Edit the **.env** file in **/var/www/html/firefly-iii/** and change the **DB_PASSWORD** parameter to the new password you created for the mysql firefly user.

        `sudo nano /var/www/html/firefly-iii/.env`

         DB_CONNECTION=mysql

         DB_HOST=localhost

         DB_PORT=3306

         DB_DATABASE=firefly

         DB_USERNAME=firefly

         DB_PASSWORD=secret_firefly_password
         
         

================================

If you have permission issues when running the .sh script without sudo, then try this:

Here is how to make the .sh files executable:

1. You can right click the file and go to the **Permissions** tab and tick the checkbox that says **"Allow executing file as program"**.

OR

2. Use the following terminal command to make the file executable:

`chmod +x /path/to/your/filename.sh`

## Acknowledgements

JC5 for this awesome firefly-iii financial management app :)
