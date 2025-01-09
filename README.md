# linux_cyber_unit

I teach a high school Introduction to Computer Programming course. In that course, I introduce some very basic cybersecurity concepts in a short unit that begins with an intro to linux and concludes with working through modules in tryhackme.com.  
This repro is a general discription of that unit.

# Linux Cyber Unit

## Unit Outline
- Hardware 
- Linux Basics and Nano (details in [linux_basics_nano.md](../linux_basics_nano.md))
- Website Hosting and SSH (details in hosting_ssh.md)
- Terminus (links in [terminus directory](../terminus))
- <a href="https://tryhackme.com/" target="_blank">TryHackMe.com</a>
<!--- [TryHackMe](https://tryhackme.com)-->

## Hardware
Teachers often make the most of the equipment that is available to them.  
For these specific instructions, I use:
- Raspberry Pis
- MicroSD Cards
- The monitor, keyboard and mouse from my lab desktops
- An old home internet router (for web hosting and ssh section)
If you ave different equipment, I hope you will be able to adapt these instructions to suit your needs.

### Raspberry Pi [raspberrypi.org](https://www.raspberrypi.org)
I use Raspberry Pis for this unit, but any linux desktop should work.  
My predecessor had a class set of Raspberry Pi 3B+. Those are fine and are pis that are in the pictures.
I have upgraded to RP 5 and the 5s are significantly faster making them easier to use.

If funding is an issue, you should be able to do this with any pi that has wifi and linux desktop.
I believe even a Pi Zero W would work, but I haven't tested it.  Pico might not have a desktop.

### MicroSD Cards
Each pi needs a microSD card to hold the operating system.  
I assignment each student their own microSD, so they have the opportunity to have their own os.
They keep their card in a numbered card case. They install them at the beginning of class and remove it at the end.  This is ideal if possible.  If they share microSD cards, the second student will not get to do some of the set up.

### Monitor, keyboard, mouse
We connect the pis to the monitor, keyboard and mouse that is already at their desk.

### Home Router
We use an old home router to create a LAN (local area network) to locally host their simple websites.
I do not connect this router to the internet. This eliminates COPPA compliance concerns, because the browsers in a raspberry pi will not have safe search required.  And you will not need internet for this unit.

## Linux Basics and Nano
Details for this section are in linux_basics_nano.md
The purpose of this section is to provide an opportunity for learners to: 
- play around with linux desktop by editing their preferences...
- begin using some basic terminal commands (ls, cd, mkdir, touch...)
- create a directory and files on the desktop using terminal commands
- use nano editor to edit .txt and .py files inside the terminal

## Hosting an SSH  
Details for this section are in hosting_ssh.md
The purpose of this section is to provide an opportunity for learners to:
- learn about servers and clients through locally hosting a website
- 
- and its fun for them to make a simple site that their classmates can pull up on their pi

## Terminus 
In the terminus directory is a file [terminus.md](../terminus/terminus.med) that has additional information.
The directory also has files with directions for this activity.

## TryHackMe
TryHackMe is great resource for learning about cyber security.

### Instruction  
The presentation of the website is user freindly and visually appealing.
They provide instruction sections that are clear and approachable for beginners. 
They offer learning paths that can help learners align their learning with their goals.

### Virtual Machines  
The challenges provide hands on learning using virtual machines (VMs) with linux and Windows machines allowing learners to experience both sides of attacks and defense.  
These activities are very realistic and very engaging for students.  
Since my students have gained some linux experience, they are able to confidently jump into these activities.  

### Cost  
To provide this level of quality, TryHackMe does have a pay level and a free level.
The free level is limited on use time per day and access to some lessons.  
I just use the free level, since the course that I teach is not cyber security.  

If I taught cyber security with upper level students, I would strongly consider getting the paid level.    
It is very expensive, but the quality is much better than any other education platform for cyber that I have used. 






