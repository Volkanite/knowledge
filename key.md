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
