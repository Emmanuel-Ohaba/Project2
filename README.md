# Project2
E-commerce platform deployment with Git, Linux and AWS
TASK 
1. I went to my vscode terminal and cd to Desktop. In Desktop, I created a directory called MaeketPeak_Ecoomerce and also cd into the directory. While in MarketPeak_Ecommerce, I initialized the repository.I did so with mkdir MarketPeak_Ecommerce cd - MarketPeak_Ecommerce - git init respectively.
2. I downloaded the website template which was provided at darey.io and extacted the file in my local computer. I copied the files and added the extracted files to the folder created.
3. I configured my details using the git cofig –global user.name “Your username” and git config –global user.email “Your email address” to input my rmail
4. I opened the folder (MarketPeak_Ecommerce) on my vscode and then stagged the files using git add .
5. I committed the files using git commit -m "message" and proceeded to push these file using the git push command to my remote repository i.e. git push -b git push main.
6. Before pushing the files, I linked my local repository to my GitHub using the command git remote add origin “HTTPS URL”
7. After linking I pushed the file to my remote repository.
8. I then logged into my AWS account and launched an EC2 instance using Amazon Linux as my AMI.
I connected to the instance from my Ubuntu terminal using SSH.
9. I needed to connect my EC2 to my GitHub and before doing so, I needed to have an SSH key pair on my GitHub.
10. On my terminal, used the command ssh-keygen to generate a ssh key.
11. My SSH public key was saved in /home/ubuntu/.ssh/id_rsa.pub so I cat into the file to copy the content. I then added the SSH key pair to my GitHub account.
12. I then installed Apache web server on my EC2 instance using the sudo yum command. This is because Amazon Linux is a fedora-based system. The commands used are below.

sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
I added these commands one after the other.

13. I cleared the default httpd directory where the website code files are stored and replaced them with the contents of MarketPeak_Ecommerce files using the commands blow 

sudo rm -rf /var/www/html/*
sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/

I used the command to reload the httpd service with the command

sudo systemctl reload httpd

14. I then added a new security group that enabled http from anywhere.
15. I copied my public IP address from my EC2 and entered it on my browser and the website was live. 
16. I created a new branch callled development and checked into it using the commands

git branch development
git checkout development

I used vim and implemented changes to the files and proceeded to stage, commit and push the files using the various git commands.

17. I created a pull request and merged the development branch to the main branch using the command

git checkout main
git merge development

I then used git push origin main to ensure that the local main branch now contains the updates and is pushed to the remote repository on GitHub.

18. I used the command git pull origin main to pull the latest changes into the AWS EC2 instance. I then used the command sudo systemctl reload httpd to restart the Apache web server.

19. I entered my public IP address on my web browser and the changes were effected.
