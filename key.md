Check if ssh-agent is running:

     eval "$(ssh-agent -s)"  

Add ssh key:

     ssh-add ~/.ssh/id_ed25519

Copy key to clipboard:

     clip < ~/.ssh/id_ed25519.pub
