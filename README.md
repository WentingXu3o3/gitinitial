# gitinitial
This is how to link your github account for the first time

1. Check for Existing SSH key
```
ls ~/.ssh
```
Look for files named id_rsa and id_rsa.pub or similar. 
If you don't have these, you'll need to generate a new SSH key.

2. generate a new SSH Key

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
   
"your_email@example.com" change it to your github account 
You can not to set a passphrase. enter to pass
If succed, you will see a interesting image figure

if failed, probably becuase your ssh is not in chmod 700 mode.
so
```
chmod 700 ~/.ssh
```
if still failed, then move right now .ssh and build a new one
```
mv ~/.ssh ~/.ssh_copy
```
```
mkdir ~/.ssh
chmod 700 ~/.ssh
```
and then repeat the step 2. 

3.Start the SSH Agent and Add Your Key:
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

4.Add the SSH Key to Your GitHub Account:
```
cat ~/.ssh/id_rsa.pub
```
5.Go to YOUR GitHub and find your account SSH settings, Click New SSH key, provide a title, and paste your key into the "Key" field.

6.Test the SSH Connection:
```
ssh -T git@github.com
```
And you will see 'Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.

7. if failed, do below again
```
chmod 600 ~/.ssh/config
chmod 700 ~/.ssh
```

8.Clone the Repository Again:

```
git clone git@github.com:xxx
```


