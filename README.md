# SSH connect local machine with github

Here I am goona record the method to connect code in local machine with github, so you can switch between branches, and code will also be shown in you local machine.


So suppose we have a project in our local machine.

## initialize git in the diectory of the folder:

git init

## add all file in the current folder to the warehouse:

git add .

## commit the files:

git commit -m "your own comments"

## Need to be done on github:

1. create a new repository for this project

2. copy the ssh link for the repository

3.git remote add origin + what you have copied

## pull and push

git pull origin main/anothor_new_branch

git push -u origin main



## error you might meet:

jiayang@y7000p:~/Desktop/cloudcomputing_lab/concurrency_programming$ git pull origin master  
The authenticity of host 'github.com (140.82.112.4)' can't be established.  
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.  
Are you sure you want to continue connecting (yes/no)? y
Please type 'yes' or 'no': yes  
Warning: Permanently added 'github.com,140.82.112.4' (RSA) to the list of known hosts.  
git@github.com: Permission denied (publickey).  
fatal: Could not read from remote repository.  
  
Please make sure you have the correct access rights  
and the repository exists.  

So if you meet this kind of error, it might because you need a ssh key:  
When working with a GitHub repository, you'll often need to identify yourself to GitHub using your username and password.   
An SSH key is an alternate way to identify yourself that doesn't require you to enter you username and password every time.  
SSH keys come in pairs, a public key that gets shared with services like GitHub, and a private key that is stored only on your computer.   
If the keys match, you're granted access.  
The cryptography behind SSH keys ensures that no one can reverse engineer your private key from the public one.  

So you need to use: 

ssh-keygen -o -t rsa -C "your@email.com"

to generate a key pair.  

When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.  

At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases".  

Then you need to add the ssh key to the github:  

check you key by : cat ~/.ssh/id_rsa.pub  




