# Using Putty to SSH into Fedora Linux

## Objective
In this project I will demostrate how to ssh into Fedora Linux using Putty. I am running Fedora on a virtual machine, but this would often be used to remote into a linux server to change some config or do something with the file system

### Skills Learned
-How to setup openssh in Fedora

-How to SSH into a remote server

### Tools Used
-Putty

-Fedora 43 Workstation

-Virtualbox for my virtual machine

## Steps
In this project I will demostrate how to ssh into Fedora Linux using Putty. I am running Fedora on a virtual machine, but this would often be used to remote into a linux server to change some config or do something with the file system

Setup

First, we need to make sure our Fedora machine is ready to receive SSH input. Again, normally on a server you would already have this setup, but I want to make sure that this virtual Fedora workstation
First thing we need to do is verify OpenSSH is on Fedora

```
sudo dnf install -y openssh-server

Enter sudo password
```

<img width="975" height="383" alt="image" src="https://github.com/user-attachments/assets/a86af4cb-b380-4ef2-8f87-70819e79cf73" />

*Ref 1: screenshot of installing openssh*
 
Now we want to enable SSH and verify that it is enabled:
```
Sudo systemctl enable –now sshd

After that we type systemctl status sshd
```
We can see from the picture that it is active and running

<img width="1022" height="508" alt="image" src="https://github.com/user-attachments/assets/3ace5196-8cf2-48e4-826d-86a2a82689c7" />

*Ref 2: OpenSSH Running*

Now we need to check the firewall to make sure that is all setup
```
Sudo firewall-cmd –permanent –add-service=ssh
```
<img width="1037" height="347" alt="image" src="https://github.com/user-attachments/assets/654f94d4-dc98-42ff-b3ce-bc42f068726a" />

*Ref 3: Firewall Setup*

Next, we need to get the IP address of our Linux machine. Again, if you were logging on a server you would probalby already have this information but for out purpose
```
Ip add
```
<img width="975" height="395" alt="image" src="https://github.com/user-attachments/assets/8324383f-e025-45bc-a0e0-8b8994b6d680" />

*Ref 4: Obtaining IP Address*

Now that the Linux side is setup we need to Logout if we plan to use the same name and password as this one

Now we goto to our Putty and click on it to open

<img width="647" height="619" alt="image" src="https://github.com/user-attachments/assets/fbf435e2-99c1-4749-9e1c-e507fcd3aecf" />

*Ref 5: Putty Setup*

Enter the ip address into the host name box and make sure it is on port 22
 
Now log with your name and password for your Fedora Account.

<img width="834" height="561" alt="image" src="https://github.com/user-attachments/assets/b30f261e-f1d3-448d-85bc-5e7e15593d39" />

*Ref 6: Logging into Fedora through Putty*

To show that we are on the same Linux machine we are going to create a directory called Test and then a file called flag. 
We will type “this is a flag to show we SSH’d into this”
Now we can exit out of Putty  and go back to our Fedora and re login
If we navigate to our folders we will see the Test folder and our flag file. If we open it we will see what we wrote.

<img width="944" height="434" alt="image" src="https://github.com/user-attachments/assets/3ef677ce-1f43-45cf-bf72-e71b8508afd4" />

*Ref 7: Verifying Test Folder and File*

This concludes this post on how to use Putty SSH to log into a Linux machine

