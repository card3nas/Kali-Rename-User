# Kali-Rename-User

These steps will take you on completely renaming the original kali user (ID 1000) into the name of your choice. 

## Step 1
Log in to the default kali user and open a terminal. You can see what user you are logged in as by using the command 
```bash
whoami
```

![image](https://user-images.githubusercontent.com/42426317/161457625-eaa3663e-933d-43ba-b9be-00a1befbd1b5.png)

 ## Step 2
 Verify the user ID. You can check the user id by looking in the ```passwd``` file. 
 Type the command 
 ```bash
 cat /etc/passwd
 ```
 then look for your user name - in most cases it is kali and it looks like this. 
 
![image](https://user-images.githubusercontent.com/42426317/161457583-bc1a040e-ac8e-4f8e-9e71-d6dedc5533d4.png)

## Step 3
Enable the ```root``` user. 
The first step in doing this is to change the password for root. 
From your default (kali) user, type the following command to switch user and become root: 
```bash
sudo -i
```

![image](https://user-images.githubusercontent.com/42426317/161458008-81dc05bc-b8b9-4633-ab89-85733393c42b.png)

## Step 4
Now that you are in as root, type in this command to change the password. Follow the directions as prompted.
```bash
passwd root
```

![image](https://user-images.githubusercontent.com/42426317/161458102-0b44a55e-017c-4e7c-b8e2-793a005f1d4b.png)

## Step 5
Exit out of the terminal, log out from using the ```kali``` user.

## Step 6
Log in as ```root``` using the new password that was set in step 4.

## Step 7
Lets change the name of the home directory with this command: 
```bash
sudo usermod -l <newUsername> -d /home/kali -m kali
```

## Step 8
Change the name of the user group
```bash
sudo groupmod -n <newUsername> kali
```

## Step 9
Some applications will show an error when chaning the default home directory name. 
To resolve any (anticipated) issues, lets create a symbolic link from the new to the old directory name. 
```bash
sudo ln -s /home/<newUsername> /home/kali
```

## Step 10
Change the display name (firstName lastName). This is the name you want to display on your login screen / elsewhere on the system. 
```bash
sudo chfn -f "new Username" newUsername
```

## Step 11
Check all your new changes. 
```bash
cat /etc/passwd
```
You should now see all the new username, working directory and group name have changed, but the UserID has remained the same. 

## Step 12
Reboot your system and log in as your new user (with your new username). 
You will use your ```SAME PASSWORD``` that you were using with the old username. 

Once again, after you log in using your new user name, you can verify the changes you made. 


===========================================================================
### Credit 
The steps are taken from Tech Dhee's video https://youtu.be/k2ZeUkHZSn0 .


===========================================================================

[Coram Deo](https://www.ligonier.org/learn/articles/what-does-coram-deo-mean) !
