Step 1, Create SSH key:

    ssh-keygen -t ed25519 -C "your_email@something.com"
    
Step 2, Enter passphrase for key

Step 3, Check if ssh-agent is running:

     eval "$(ssh-agent -s)"  

Step 4, Add ssh key:

     ssh-add ~/.ssh/id_ed25519

Step 5, Copy key to clipboard:

     clip < ~/.ssh/id_ed25519.pub
