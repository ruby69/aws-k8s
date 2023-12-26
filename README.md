# AWS-K8S

### Initialize EC2 instance
> After running wsl, copy the 'cert.pem' file for aws ec2 to any wsl's directory then connect to instance. 
```
app:~$ ssh -i ~/ec2/cert.pem ec2-user@10.0.0.1
```
![001](./images/001.jpg)

> Create new account and initialize it.
```
[ec2-user@ip-10-0-0-1 ~]$ sudo adduser app
[ec2-user@ip-10-0-0-1 ~]$ sudo passwd app
Changing password for user app.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.

[ec2-user@ip-10-0-0-1 ~]$ sudo cp -rf /home/ec2-user/.ssh/ /home/app/.ssh/
[ec2-user@ip-10-0-0-1 ~]$ sudo chown -R app:app /home/app/.ssh

[ec2-user@ip-10-0-0-1 ~]$ sudo visudo
...
## The COMMANDS section may have other options added to it.
## Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
app     ALL=(ALL)       ALL
...
```
![002](./images/002.jpg)

> Connect new account.
```
app:~$ ssh -i ~/ec2/cert.pem app@10.0.0.1
```
![003](./images/003.jpg)

> To register profile in Windows Terminal, use the below command line.
```
C:\Windows\system32\wsl.exe ssh -i /home/app/ec2/cert.pem app@10.0.0.1
```