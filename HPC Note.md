For many of you it will be usefull to use DTU HPC, since this gives you acces to more computing power (and it might also show useful for other courses later on)

In the following note you will gain some information arround accessing the HPC, storage on the HPC and some more specific information around tensorflow cuda and other relevant topics. 

This note is based on the official [HPC page](https://www.hpc.dtu.dk) which has many good tutorials and help pages, so use it. 

One note you can start off to look at if you are interested is the [AI/DL/ML corner](https://www.hpc.dtu.dk/?page_id=4788) which focuses on the use of HPC wrt. machine learning. 

Recommended procedure
This is for those of you new to all of this 
- Use Visual Studio Code for working on your project, since it makes accesing and working on your project on the HPC a lot easier.
- this also means that you will use command line access
- use VPN as security measurement
- 
# Accesing the HPC
*Relevant Links*
- [Accessing the LSF 10 Cluster](https://www.hpc.dtu.dk/?page_id=2501)
- [SSH and ThinLinc using ssh-keys](https://www.hpc.dtu.dk/?page_id=4317)
- [Cisco VPN DTU](https://itswiki.compute.dtu.dk/index.php/Cisco_VPN) (The wiki is specific for compute but applies for other departments)
- [OpenVPN](https://itswiki.compute.dtu.dk/index.php/OpenVPN)

There are two ways in which you can access the HPC 
1. command line : ssh access
2. Graphical interface: ThinLinc

On top of that there are some security measurements you have to take into account when accessing the HPC 

When you are on DTU premises (using DTUs WiFi or on the computers) you can use both of the above methods without further problem. When you are working remotely you have again two options 
1. VPN 
2.  ssh key (slightly different from ssh access above)

## On DTU premises 

### command line 
you just have to open a terminal and write 
`ssh userid@login1.gbar.dtu.dk` or  
`ssh userid@login1.hpc.dtu.dk` or  
`ssh userid@login2.gbar.dtu.dk` or  
`ssh userid@login2.hpc.dtu.dk`
you are then asked to enter you DTU password. 

NOTE: after accessing the HPC you are on a LOGIN NODE, you should NOT be running any scripts from here. 
Get used to accessing an interactive node right away. 
write 
```terminal
linuxsh
```
in the command line (for a interactive CPU node)

### ThinLinc 
THinLinc is a graphical Interface, and can f.eks. be helpful if you work well with visual directories etc. 

The instructions for thinlinc are provided by DTUS gBar supåport: https://www.gbar.dtu.dk/index.php/faq/43-thinlinc

To download visit the website the offical cendio website: https://www.cendio.com/thinlinc/download/

In the three required fields are

**Server**: _thinlinc.gbar.dtu.dk_  
**Username**: _DTU userid_  
**Password**: _DTU password_

## Using VPN 

If you decide to use VPN the setup is very simple and you do not need to be at DTU for this. 
#### VPN setup 
To setup the VPN you need to follow the instructions in  [Cisco VPN DTU](https://itswiki.compute.dtu.dk/index.php/Cisco_VPN) (The wiki is specific for compute but applies for other departments) for your OS system. 
If you encounter problems with Cisco AnyConnect, you can also try with [OpenVPN](https://itswiki.compute.dtu.dk/index.php/OpenVPN)

#### Access the HPC command line and Thinlinc
In both cases the acces is the same as when you are on DTU premises.


## Using ssh-key

The guide for for generating an ssh-key can be found on the official HPC page : [SSH and ThinLinc using ssh-keys](https://www.hpc.dtu.dk/?page_id=4317)

**Note:** the guide below requires that you – during the setup process – are either connected to a DTU network on Campus, or via VPN (see DTU Inside for the [VPN setup](https://www.inside.dtu.dk/en/medarbejder/it-og-telefoni/it-support-og-kontakt/guides/remote/vpn-cisco-anyconnect)).

Start out by looking at the requirements mentioned on the page. (https://www.hpc.dtu.dk/?page_id=4317) 
#### Setup: Step by step guide for MacOS, Linux, Windows with ssh (openssh)

1. Create a private/public key-pair for connecting to our setup
Open a terminal on your local machine, and then write:
```terminal
cd
mkdir -p .ssh
cd .ssh
ssh-keygen -t ed25519 -f gbar
```
> that is we create an .ssh folder in which we want to create an ssh-key

the last command is asking for a passphrase (password for the key), so **please chose a new “good enough password”, which is _NOT_ your DTU password** (and also not any old password, which you have used at DTU before, because they might be compromised, too).

```terminal
$ ssh-keygen -t ed25519 -f gbar
Generating public/private ed25519 key pair.
Enter passphrase (empty for no passphrase): *********
Enter same passphrase again: *********
Your identification has been saved in gbar
Your public key has been saved in gbar.pub
The key fingerprint is:
SHA256:Pm2XrdUigYlcCMEbXUEA+1ze53IUBBOPUU92uvxiQF8 s123456@nowhere
The key's randomart image is:
+--[ED25519 256]--+
| .++.++.=+o +|
| oo.. * =.|
| .o. o o + E|
| .+ = = o + |
| S + + * |
| . . O o |
| o o = O o|
| o . B o |
| . |
+----[SHA256]-----+
```
Now you have two files in the .ssh folder:  gbar and gbar.pub, we can check them out through the following command

```terminal
$ ls -l gbar*
9051786 4 -rw-------. 1 s123456 s123456 464 Aug 21 14:45 gbar
9054680 4 -rw-------. 1 s123456 s123456 99 Aug 21 14:45 gbar.pub
```
The gbar file contains your private key, so make sure it stays private (and **under no circumstances upload this thing to a git-repository or similiar(!!!) by accident or on purpose**).

The public-key is in the file gbar.pub, the content of which you need to copy into your .ssh/authorized_keys file on our setup (your cluster account) .

2. Copy the file to the cluster
- *If you already have a .ssh/authorized_keys in your HOME directory on the cluster*:
  Login to the cluster (when connected to a DTU network, either on Campus or via VPN) and just add the new entry to this file.
  You can for example just append a new entry with doing a
  ```terminal
  cat >> .ssh/authorized_keys
  ```
  and then paste the “public key” into the terminal and then finish
  this with \<ctrl\>-d to close the file.
  Or if you prefer you can use any plain text editor on the cluster to edit the file .ssh/authorized_keys.

- *If you don’t have such a file yet*, then you can just execute these two commands from your machine:
  Make sure that you are on a DTU network, and then copy the public-key into the right place:
  ```terminal
  # create the folder (with the right permissions), in case it doesn't exist 
  ssh s123456@transfer.gbar.dtu.dk mkdir -m 700 -p .ssh
  # copy the public key into the right place
  scp gbar.pub s123456@transfer.gbar.dtu.dk:.ssh/authorized_keys
  # fix the permissions of the file (need to be '600', i.e. only 'rw' by you)
  ssh s123456@transfer.gbar.dtu.dk chmod 600 .ssh/authorized_keys
  ```

#### Accessing via command line

3. How to connect to the system with ssh and the ssh-key
Now you should be able to connect to our setup with the key:
```terminal
ssh -i ~/.ssh/gbar s123456@login.hpc.dtu.dk
```
and it should ask for the your ssh-key-passphrase and your DTU-password afterwards and then you should have a login-shell on our login-node.
Use “exit” to exit or press \<ctrl\>-d to return to your current shell on your local machine.

4. Optional: simplify the ssh-login procedure (**recommended**)
To make it a bit easier and type less, you can
create a file named .ssh/config  in your HOME directory on your local machine, with something like that in it

```doc
--------------snip-------------------
Host gbar1
User s123456
IdentityFile ~/.ssh/gbar
Hostname login1.gbar.dtu.dk
---------------snip------------------
```
then you can just connect via ssh with the simple command
```terminal
ssh gbar1
```
and will ask for your passphrase for your key and your DTU-password (as the second factor) and you
are connected.

#### Accessing via ThinLinc
**How to connect to the system using the ssh-key with the ThinLinc client**
You have to enable public-key-authentication within the ThinLinc-client and then you just use the  
“gbar” public/private key as the authentication method.

Start the ThinLinc-client

-> Options  
-> Security  
-> Authentication method: “public key”  
-> “OK”

Choose the “gbar” file as the “key”, and from now on you are using the key-pair for authentication and it will ask you  
for the passphrase of your key-pair.

The webinterface of our ThinLinc-setup is at the moment only reachable when connected from inside the DTU-network.

# Using the HPC to run scripts
As mentioned previously, after entering the cluster you will be in a LOGIN NODe, you should NOT be running any scripts from here. 
Get used to entering an interactive node right away by running 
```terminal 
linuxsh
```


