# gitinitial
This is how to link your git count for the first time

1. Check for Existing SSH key
'''
ls ~/.ssh
'''
Look for files named id_rsa and id_rsa.pub or similar. If you don't have these, you'll need to generate a new SSH key.
2. generate a new SSH Key

'''
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
'''
   
"your_email@example.com" change it to your github account 
3.Start the SSH Agent and Add Your Key:
'''
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
'''
You can not to set a passphrase. enter to pass
4.Add the SSH Key to Your GitHub Account:
'''
cat ~/.ssh/id_rsa.pub
'''
5.Go to YOUR GitHub and find your account SSH settings, Click New SSH key, provide a title, and paste your key into the "Key" field.
6.Test the SSH Connection:
'''
ssh -T git@github.com
'''
And you will see 'Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.
7.Clone the Repository Again:
'''
git clone git@github.com:xxx
'''
