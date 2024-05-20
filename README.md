# gitinitial
This is how to link your github account for the first time

1. Check for Existing SSH key
```
ls ~/.ssh
```
Look for files named id_rsa and id_rsa.pub or similar. If you don't have these, you'll need to generate a new SSH key.
3. generate a new SSH Key

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
   
"your_email@example.com" change it to your github account 

4.Start the SSH Agent and Add Your Key:
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```
You can not to set a passphrase. enter to pass
5.Add the SSH Key to Your GitHub Account:
```
cat ~/.ssh/id_rsa.pub
```
6.Go to YOUR GitHub and find your account SSH settings, Click New SSH key, provide a title, and paste your key into the "Key" field.
7.Test the SSH Connection:
```
ssh -T git@github.com
```
And you will see 'Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.
8.Clone the Repository Again:
if you want init it.
```
git init
```
and try to clone
```
git clone git@github.com:xxx
```


