# Hosting and SSH 

The purpose of this section is to provide an opportunity for learners to:
- learn about servers and clients through locally hosting a website
- learn about IP address (IPv4, IPv6, DNS, static IP addresses...)
- experience headless access to a linux terminal through ssh
- run a single python http server and see the traffic coming to their website/server
- also it's fun for them to make a simple site that their classmates can pull up on their pi

## Outline
- [Basic HTML](#basic-html) 
- [Viewing the Site](#viewing-the-site)
- [Local Hosting](#local-hosting) using python http.server
- [Viewing Locally Hosted Sites](#viewing-locally-hosted-sites)  
- [Static IPv4 Address](#static-ipv4-address) on a raspberry pi
- [SSH Basics](#ssh-basics)
- [Edit and Host Site Headlessly](#edit-and-host-site-headlessly) using ssh, terminal and nano
- [History and Grading](#history-and-grading)

## Basic HTML
In this activity, we host very basic websites remotely.  
So the first step is to create a very basic website. 
I have them start by creating a new directory for the site and cd into the directory.  
In the previous activity for basic linux, we created files using *touch* then we used nano to edit it.  
In this activity, I usually show them that if you nano into a file that does not exist, nano will create the file.  
I have them nano into *index.html* to create a html file named index. I explain that web server look for index.html as the home page.  

![html 1](img/html/html1.png)

Next, I have them create a very basic site in nano.  
I explain the purpose of the boiler plate tags and that we are leaving a lot of boiler plate off.  
(If your class has worked with html, I think it would be good to create a more full site. My course is a python programming course, so I just have them create the most basic site possible.)  
Then, save their changes using Control+O.  

![html 2](img/html/html2.png)

[Back to Outline](#outline)
## Viewing the Site
After the site is created and saved, I show them a couple of ways to view the site on their machine.  
I start by having them open the site from the desktop by clicking on the website directory then double clicking on the html file.  
If your pis are low powered like my raspberry pi 3B+, this the sites can be slow to open.  

![html 3](img/html/html3.png)

Next, I have them close that browser.  
Then, they launch the browser and site from the terminal using the *firefox index.html* command  
(they must be in the site directory for firefox to find it)  
I explain that firefox in a program and using the *firefox* command is just like starting a command with *nano* or *python*.  

![html 4](img/html/html4.png)

After they open their site with *firefox*, the terminal will be running that site and nothing else. (we discuss this too)  
To close the site and get back to the regular terminal, we use Control+C to kill the process. (we discuss using Control+C to end processes)  

![html 5](img/html/html5.png)

Then we use the *clear* command to clear the terminal to start the next steps. 

![html 6](img/html/html6.png)

[Back to Outline](#outline)
## Local Hosting 
Now that the students have a basic website, we host them locally in using an old home router that I have in my classroom.  

I have the student connect their pis to the router. My router is not connected to the internet, so they get a notice of no internet.  I explain to them that we will just use the router to create a Local Area Network (LAN). Using a LAN lets the students host their sites and experience running a server without having to worry about COPPA and having browsers that do not require Safe Search.  

Raspberry Pis are completely open, so I would strongly recommend using a LAN and not connecting pis to the internet.  
This process creates a lot of opportunity for explanation and discussion about internet, routers, networks, COPPA...

![router](img/router.png)

Once the students are connected to the router, I have the students look at their IP address by hovering over the internet connection.  

We discuss IPv4 vs IPv6, how ip addresses work, why the first numbers are the same, that the router provides the ip...  
(I am not going into a lot of detail on these discussions, because these instructions are already lengthy.  But, you should be able to find a lot of information about networking and ip addresses by searching the internet.)  

After they have seen their ip address, I have them host their site using python's built-in http.server.  
(Python is preinstalled with all raspberry pi distros.)
While inside the website directory, we use the command *python -m http.server* 
This starts the server and serves their index.html page using the default port of 8000.

![hosting 1](img/hosting/hosting1.png)

[Back to Outline](#outline)
## Viewing Locally Hosted Sites 
Once the server starts, I have them open a browser and type in the url of *their_ip:8000* and they should see their site.  
Here I discuss ports, web addresses, DNS... But, in a basic way.

I also point out that they can now see each others' sites by changing the url to someone else's ip address.  
(they like seeing the other sites)  
And I point out that they can see the traffic of the request to their server.  

![hosting 2](img/hosting/hosting2.png)

This picture show me accessing the site from another computer.  

![second_computer_view](img/ssh/second_computor_view.png)

When we finish playing with this, which usually they like to play with it for a while.  
I have them stop their server using Control+C and refresh their browser page, so they can see that the browser can no longer connect to their server.  

![hosting 3](img/hosting/hosting3.png)

[Back to Outline](#outline)
## Static IPv4 Address 
You will need to know the IPv4 address of your pi in order to get remote access to its terminal through ssh.  
The router assigns IPv4 addresses to devices that connect to it. The IPv6 address is provided by your internet provider, but we are not connecting to the internet so we will only be dealing with IPv4.  
This is a good opportunity to discuss IPv4 and IPv6.  

Your router will also change ip addresses of device periodically for security reasons.  
This creates an issue for headless access. If the ip address changes, you will need to find the new ip to be able to use ssh.  

To solve this issue, we can set a static ip address for the pi. 
Then the pi will communicate its static ip to the router when it connects. If that ip is available, the router will use that ip for the pi.  
This is a good time to discuss static ip addresses.  

To set a static ip on a pi, click on the wifi icon on the taskbar of the pi and select Network Connections.  
Select your router. (the example in the picture is NETGEAR73)  
Then click the settings gear icon.  

![static_ip_1](img/static_ip/static_ip1.png)

Select the IPv4 Settings tab. 
Change the Method to Manual.  
Click the Add button.

![static_ip_2](img/static_ip/static_ip2.png)

I have students add their current ip address, netmask and gateway to lock in their current ip address.  
Their ip address can be found by hovering over the wifi icon. (it probably starts with 192.168.  )  
The Netmask should prefill for you. (it is probably 24 or 22)  
The Gateway can be found by running the *route* command in the terminal.  

You may need to do some experimenting or research to get the correct netmask and gateway for your router.  
But, those should be the same for all the devices on your router. So once you find the correct numbers, they should be the same for everyone.  

![static_ip_3](img/static_ip/static_ip3.png)

After we save the static ip address, I have the students restart their pis to make sure the ip address stayed and that it seems to function ok without errors.

[Back to Outline](#outline)
## SSH Basics 
In order to remote into your pi using ssh (**s**ecure **sh**ell), you need to enable ssh on your pi.  
Go to the raspberry icon that is located where the start menu would be, and select Raspberry Pi Configuration.  
Go to the Interfaces tab, then toggle on SSH.  

![ssh_1](img/ssh/ssh1.png)

This does make your pi vulnerable because it allows remote access, but we are not connecting them to the internet.  
This is a good time to discuss security and making sure you change default passwords for devices.  

[Back to Outline](#outline)
## Edit and Host Site Headlessly 
Secure Shell (ssh) allows us to access the terminal of the pi.  
We can do anything that we would from the terminal, but we will not see the desktop.  
Accessing only the terminal or command line without a desktop is typical for accessing servers or remote machines.  

To be able to ssh, your students will need to have terminal or command line (Windows name for terminal) accesses for a device.  
Schools usually do not allow students to have command line or terminal access. We have my computer on a VLAN so that we can give them command line access. If you are not able to do that, you could ssh from another raspberry pi to access the pi with their website on it.  
On you could skip this portion of the unit. Even without ssh, the prior sections have given them practice with linux, running a server, html, ip addresses...

For the rest of this section, I will show you how we use ssh from PowerShell on our Windows computers to run our website server on our raspberry pi. 
In class, we power on the pis, but do not connect a monitor, mouse or keyboard to them.  

To ssh into the pi, the other device must also be on the same network as the pi, so connect it to the router.  
Open Windows PowerShell, or a terminal on a Mac or other raspberry pi.  
Enter the command *ssh your_user_name@your_ip_address*, then hit enter.  
The user name and password are the credentials that you set when you setup the pi.  

You will see a statement about a fingerprint (the pi will remember which devices remotely accessed it by saving a fingerprint). 
You need to answer *yes* to the question about continuing to connect.

Then it will ask for your password to the pi.  
**When you type in your password, the curser will not move but it is taking the password.**  
This is for security. It will feel like you are entering the password blindly.  

Next, you will see some information about Linux and raspberry pi. 
Then you should see your raspberry pi terminal begin and it will look just like your terminal in the pi.  
This is because it is the terminal in your pi.  

![ssh_remote_1](img/ssh/ssh_remote1.png)

This picture shows my pi running with a monitor and the laptop that I used to ssh into that pi.  

![ssh_2](img/ssh/ssh2.png)

Now that I am in my pi's terminal, I can run the command to start my website server.  
*cd* into the directory with your html file.  
Then use the command *python -m http.server* to start the server.  

![ssh_remote_2](img/ssh/ssh_remote2.png)

Just like before, we can now see the website by going to the url *your_ip_address:8000*.  
I do this from the browser on my Windows computer.  

![ssh_remote_3](img/ssh/ssh_remote3.png)

Now that we have started a server remotely through ssh, I have them update their site remotely.  
First, I have them stop the server using Control+C.  
Then I have them open their html file using nano.  

![ssh_remote_4](img/ssh/ssh_remote4.png)

They change something on the site. (I like to have them add today's date)  
Then save their changes and exit nano.  
Control+O > Enter > Control+X 

![ssh_remote_5](img/ssh/ssh_remote5.png)

Once they are back in the terminal, they can restart the server using *python -m http.server* and refresh their browser to see the changes.  
At this point, I usually walk around and give them a grade for completing the assignment.  

![ssh_remote_6](img/ssh/ssh_remote6.png)

Then I have them stop the server using Control+C and refresh their browser.  
This shows them that the website will not load if the server is not running.  

![ssh_remote_7](img/ssh/ssh_remote7.png)

Now that they are finished, they need to shutdown their pi.  
It is bad for any computer to just pull the plug, so we need to use the *shutdown* command in the terminal.  
For security reasons, only authorised users can shutdown a pi remotely.  

![ssh_remote_8](img/ssh/ssh_remote8.png)

To show that they are an authorised user, they must use the command *sudo shutdown* .  
If you are not familiar with sudo, you should be able to find information about sudo in linux on the internet.  
At this point, we discuss sudo and authorisation in relation to security.  

![ssh_remote_9](img/ssh/ssh_remote9.png)

The default for *sudo shutdown* is to shutdown in 2 minutes.  
You can also use *sudo shutdown now* to have the pi shutdown immediately. 

![ssh_remote_10](img/ssh/ssh_remote10.png)

Once the pi is shutdown, the ssh connection will be lost and the computer will go back to its PowerShell or terminal.  
You can see in the picture that I lost connection and my Windows PowerShell is back up.  

![ssh_shutdown_1](img/ssh/ssh_shutdown_1.png)

This picture shows that my pi is now powered off.  
In class, we connect remotely, so the students don't see the pi power off on a screen.  
But they will see that the little green light in the pi will turn to red indicating that it is shutdown.  

![ssh_shutdown_2](img/ssh/ssh_shutdown2.png)

[Back to Outline](#outline)
## History and Grading
Since students do not have access to the internet, submitting this assignment can be difficult.  
I usually grade this assignment by having students show me their edited site while I walk around and check off their names on a list.  
You could also have them show you their terminal command history by having them run the *history* command when they finish.  

![history](img/history.png)

[Back to Outline](#outline)




