Step 1, Create SSH key. The command below creates a key file named id_ed25519 in your User's folder. You can see this file in your file browser (Windows Explorer) if you navigate to C:\Users\YOUR_USERNAME\\.ssh

    ssh-keygen -t ed25519 -C "your_email@something.com"
    
Step 2, Enter passphrase for key

Step 3, Check if ssh-agent is running. If successful, it should output the process ID:

     eval "$(ssh-agent -s)"  

Step 4, Add ssh key to the list (maintained by ssh-agent). Should prompt for password you entered earlier:

     ssh-add ~/.ssh/id_ed25519

Step 5, Copy key to clipboard (the key will be available for paste, CTRL+V):

     clip < ~/.ssh/id_ed25519.pub

Step 6, Copy to GitHub [Settings](https://github.com/settings/keys) , click "New SSH key", enter a reasonable name in the Title field to help you identify the key, then paste your key in the Key field then click "Add SSH Key".

Step 7, verify if key works by comparing before and after usage:  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/key_before.png "Before use")  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/key_after.png "After use")

Step 7.1, testing the key:
- Clone one of your repositories using the SSH method. Note that you have to select SSH, as choosing HTTPS will result in normal username and password authentication:  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/ssh_clone.png)  

- First time using key should give a warning message. Type 'yes' to continue.  

![alt text](https://github.com/Volkanite/knowledge/blob/master/images/clone.png)  

- Key should then be added to list of known hosts, after which it prompts for your passphrase for the last time:  

![alt text](https://github.com/Volkanite/knowledge/blob/master/images/clone.png)
