
# set up VPN 
I am following the OpenVPN guide provided by dtu 
https://itswiki.compute.dtu.dk/index.php/OpenVPN#Windows
- [x] Visit [https://openvpn.compute.dtu.dk](https://openvpn.compute.dtu.dk/) and use your DTU initials to log in.
	- [x] **Download Current**: should be used if you would like to redownload your existing certificate. E.g. if you would like to put it on multiple computers.
- [x] Download the official OpenVPN Client for Windows: [https://openvpn.net/community-downloads/](https://openvpn.net/community-downloads/) **Note:** Needs to be version 2.5.x
	- [x] Run the setup and follow the installation steps (default installation - no need to change options). Confirm the Windows security messages.
- [x] Unpack the downloaded certs zip file and copy all files to the OpenVPN configuration folder: `C:/Users/<username>/OpenVPN/config/` (or this folder: `C:/Program Files/OpenVPN/config/`)
- [x] Run OpenVPN and double-click the icon in the task tray. Use DTU credentials to login.
- [x] verify VPN connection is working:
	- [x] web [https://vpn-test.compute.dtu.dk/](https://vpn-test.compute.dtu.dk/)
	- [x] Network shares 


# HPC read up on AI/ML corner 
AI/DL/ML corner : [https://www.hpc.dtu.dk/?page_id=4788](https://www.hpc.dtu.dk/?page_id=4788)

### First steps with the cluster
TO access the cluster the HPC website has a relevant page
- Relevant link: [https://www.hpc.dtu.dk/?page_id=2501](https://www.hpc.dtu.dk/?page_id=2501)
	under this link we are interested in command link access: [https://www.hpc.dtu.dk/?page_id=2501#CommLine](https://www.hpc.dtu.dk/?page_id=2501#CommLine)
	- however **This is outdated since it does not take ssh or VPN into account**
	- Therefore look into this link instead:  [https://www.hpc.dtu.dk/?page_id=4317](https://www.hpc.dtu.dk/?page_id=4317)
	  Now we can choose to use either VPN or ssh, but ssh is recommended when working from home only. Since that is the case for my stationary computer i will set up ssh using vpn connection 

# Set up SSH 
Note: you need to be connected to the dtu internet or connected through VPN, then you can follow the guide provided by HPC dtu : [https://www.hpc.dtu.dk/?page_id=4317](https://www.hpc.dtu.dk/?page_id=4317)
**Detailed instructions > Step by step guide for MacOS, Linux, Windows with ssh (openssh)**

### Guide from HPC.DTU.DK
1. Create a private/public key-pair for connecting to our setup
	Open a terminal, and then:
	``` terminal
	cd
	mkdir -p .ssh
	cd .ssh
	ssh-keygen -t ed25519 -f gbar
	```
	this is asking for a passphrase (password for the key), so please chose a new “good enough password”, which is _NOT_ your DTU password (and also not any old password, which you have used at DTU before, because they might be compromised, too).
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
	Now you have two files there – gbar and gbar.pub
	```terminal
	$ ls -l gbar*
	9051786 4 -rw-------. 1 s123456 s123456 464 Aug 21 14:45 gbar
	9054680 4 -rw-------. 1 s123456 s123456 99 Aug 21 14:45 gbar.pub
	```
	The gbar file contains your private key, so make sure it stays private (and under no circumstances upload this thing to a git-repository or similiar(!!!) by accident or on purpose).
	The public-key is in the file gbar.pub, the content of which you need to copy into your .ssh/authorized_keys file on our setup.

1. Copy the file to the cluster
	- If you already have a .ssh/authorized_keys in your HOME directory on the cluster:
	  Login to the cluster (when connected to a DTU network, either on Campus or via VPN) and just add the new entry to this file.
	  You can for example just append a new entry with doing a
	  ```terminal
	  cat >> .ssh/authorized_keys
	  ```
	  and then paste the “public key” into the terminal and then finish
	  this with \<ctrl\>-d to close the file.
	  Or if you prefer you can use any plain text editor on the cluster to edit the file `.ssh/authorized_keys`.
	- If you don’t have such a file yet, then you can just execute these two commands from your machine:
	  Make sure that you are on a DTU network, and then copy the public-key into the right place:

```terminal
# create the folder (with the right permissions), in case it doesn't exist 
ssh s123456@transfer.gbar.dtu.dk mkdir -m 700 -p .ssh
# copy the public key into the right place
scp gbar.pub s123456@transfer.gbar.dtu.dk:.ssh/authorized_keys
# fix the permissions of the file (need to be '600', i.e. only 'rw' by you)
ssh s123456@transfer.gbar.dtu.dk chmod 600 .ssh/authorized_keys
```
3. How to connect to the system with ssh and the ssh-key
   Now you should be able to connect to our setup with the key:
   ```terminal
   ssh -i ~/.ssh/gbar s123456@login.hpc.dtu.dk
   ```
   and it should ask for the your ssh-key-passphrase and your DTU-password afterwards and then you should have a login-shell on our login-node.
   Use “exit” to exit or press \<ctrl\>-d to return to your current shell on your local machine.

4. Optional: simplify the ssh-login procedure
   To make it a bit easier and type less, you can
   create a file named .ssh/config  in your HOME directory on your local machine, with something like that in it
```terminal
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


