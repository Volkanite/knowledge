<h1 align="center">Creating an SSH key</h1>

### Step 1
Create SSH key. The command below creates a key file named id_ed25519 in your User's folder. You can see this file in your file browser (Windows Explorer) if you navigate to C:\Users\YOUR_USERNAME\\.ssh or /home/YOUR_USERNAME/.ssh/ under Linux. (Default name is id_ed25519, you can set this name when executing the command below)

    ssh-keygen -t ed25519 -C "your_email@something.com"
    
### Step 2
Enter passphrase for key

### Step 3
Check if ssh-agent is running. If successful, it should output the process ID:

     eval "$(ssh-agent -s)"  

### Step 4
Add ssh key to the list (maintained by ssh-agent). Should prompt for password you entered earlier:

     ssh-add ~/.ssh/id_ed25519

### Step 5
Copy the public key to the clipboard (the key will be available for paste, CTRL+V):

     clip < ~/.ssh/id_ed25519.pub

### Step 6
Copy to GitHub [Settings](https://github.com/settings/keys) , click "New SSH key", enter a reasonable name in the Title field to help you identify the key, then paste your key in the Key field then click "Add SSH Key".

### Step 7
Testing the key. Take note that the key says 'Never used' :  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/key_before.png "Before use")  

- Clone one of your repositories using the SSH method. Note that you have to select SSH, as choosing HTTPS will result in normal username and password authentication:  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/ssh_clone.png)  

- First time using the key should give a warning message. Type 'yes' to continue. In the screenshot below I change to my D: drive because that is where I keep all my code. You can ignore that command. 

![alt text](https://github.com/Volkanite/knowledge/blob/master/images/clone.png)  

- Key should then be added to list of known hosts, after which it prompts for your passphrase for the last time:  

![alt text](https://github.com/Volkanite/knowledge/blob/master/images/passphrase.png)  

- After, you can run a few more verifications:

![alt text](https://github.com/Volkanite/knowledge/blob/master/images/verify.png)  

Change to the repository's directory you just cloned. I used 'knowledge' because that is the name of mine; of course yours will be different:

    cd knowledge
    
Verify that your repository is up-to-date with the remote branch:

    git status
    
If your repository's remote URL starts with 'git@github' and NOT 'https', you sucessfully set up SSH:

    git remote -v

### Step 8
'Last used...' = SUCCESS!  
![alt text](https://github.com/Volkanite/knowledge/blob/master/images/key_after.png "After use")
