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
local hosting using python http.server

![hosting 1](img/hosting/hosting1.png)
![hosting 2](img/hosting/hosting2.png)
![hosting 3](img/hosting/hosting3.png)

[Back to Outline](#outline)
## Viewing Locally Hosted Sites 
viewing locally hosted sites 

[Back to Outline](#outline)
## Static IPv4 Address 
setting a static IPv4 address on a raspberry pi

![static_ip_1](img/static_ip/static_ip1.png)
![static_ip_2](img/static_ip/static_ip2.png)
![static_ip_3](img/static_ip/static_ip3.png)

[Back to Outline](#outline)
## SSH Basics 
ssh basics

![ssh_1](img/ssh/ssh1.png)

[Back to Outline](#outline)
## Edit and Host Site Headlessly 
edit and host html site using ssh, terminal and nano

![ssh_remote_1](img/ssh/ssh_remote1.png)
![ssh_remote_2](img/ssh/ssh_remote2.png)
![ssh_remote_3](img/ssh/ssh_remote3.png)
![ssh_remote_4](img/ssh/ssh_remote4.png)
![ssh_remote_5](img/ssh/ssh_remote5.png)
![ssh_remote_6](img/ssh/ssh_remote6.png)
![ssh_remote_7](img/ssh/ssh_remote7.png)
![ssh_remote_8](img/ssh/ssh_remote8.png)
![ssh_remote_9](img/ssh/ssh_remote9.png)
![ssh_remote_10](img/ssh/ssh_remote10.png)

[Back to Outline](#outline)
## History and Grading
Since students do not have access to the internet, submitting this assignment can be difficult.  
I usually grade this assignment by having students show me their edited site while I walk around and check off their names on a list.  
You could also have them show you their terminal command history by having them run the *history* command when they finish.  

![history](img/history.png)

[Back to Outline](#outline)




