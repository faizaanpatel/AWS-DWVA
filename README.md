<h1>AWS Web Application Security on DVWA (Damn Vulnerable Web Application)</h1>

<img src="https://imgur.com/omzPnOv.png" height="80%" width="80%" alt="diagram"/>
<b>
Damn Vulnerable Web App (DVWA) is a PHP/MySQL web application that is damn vulnerable.
Its main goals are to be an aid for security professionals to test their skills and tools in a legal environment, help web developers better understand the processes of securing web applications and aid teachers/students to teach/learn web application security in a class room environment.
</b>
<img src="https://imgur.com/Qmdmzyu.png" height="80%" width="80%" alt="diagram"/>

<h2>Description</h2>
In this project, I setup an EC2 Instance on AWS with an HTTP server running on port 80. We then use docker to dock the server on a Kali Linux terminal to host the sever. Lastly we use DVWA to test vulnerabilities via Command Execution. This is a step by step guide so feel free to follow along! 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>PHP</b> 
- <b>MySQL</b>

<h2>Environments Used </h2>

- <b>Oracle VirtualBox</b>
- <b>DVWA</b>
- <b>AWS</b>
- <b>Kali Linux</b>

<h2>Program walk-through:</h2>

<p align="center">
First we will create an Amazon EC2 Instance with SSH and HTTP (Port 80) running: <br/>
<img src="https://imgur.com/hKzlcnW.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Then we will start our Kali Linux VM via VirtualBox:  <br/>
<img src="https://imgur.com/W52mjHy.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
I used my key pair to ssh into the ec2 public ipv4 address: <br/>
<img src="https://imgur.com/aHpu2HN.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Then I updated yum and installed docker, yum is a package in linux that manages dependencies:  <br/>
<img src="https://imgur.com/A5kouXv.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
I started the docker service then ran the DVWA on the server:  <br/>
<img src="https://imgur.com/xBeH4JC.png" height="80%" width="80%" alt="set up"/>
<br />
<br />
Now we can search the public DNS that was given on AWS and sign in using the defult credentials, Username:"admin" Password:"password":  <br/>
<img src="https://imgur.com/ngY91LM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now we will click on DVWA Security and make the vulnerability level to low, and then click Command Execution :  <br/>
<img src="https://imgur.com/OXhNgKc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/SKwgqil.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/K3Su883.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Below we are going to do a simple ping test using the web interface. So in our case the local host:  <br/>
<img src="https://imgur.com/jZQpAzN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now I use the "cat /etc/password" command. Notice that either a messaging saying illegal IP address was displayed or nothing was returned:  <br/>
<img src="https://imgur.com/fKlJwXM.png" height="80%" width="80%" alt="Cyber Attack Event Management"/>
<br />
<br />
Now I use the IP address with "cat /etc/password". Notice that we are now able to see the contents of the /etc/passwd file.:  
<br/>
<img src="https://imgur.com/2toazKh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Using the "IP address; cat /etc/passwd | tee /tmp/passwd" we are not only displaying the contents of /etc/passwd on the webpage, but also we are copying the /etc/passwd file to the /tmp directory:  <br/>
<img src="https://imgur.com/U2PMemG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
This Concludes This AWS Web Application Security on DVWA Project!
NOTE: You can go through the DVWA web application and test more vulnerabilities to gain new experiences!  <br/>
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
