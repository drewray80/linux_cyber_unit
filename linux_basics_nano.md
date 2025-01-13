# Linux Basics and Nano

The purpose of this section is to provide an opportunity for learners to:
- play around with linux desktop by editing their preferences...
- begin using some basic terminal commands (ls, cd, mkdir, touch...)
- create a directory and files on the desktop using terminal commands
- use nano editor to edit .txt and .py files inside the terminal

## Outline 
- [Raspberry Pi Setup](#raspberry-pi-setup) and intro to linux
- [Basic Terminal Commands](#basic-terminal-commands) and directory navigation 
- [Create a Directory](#create-a-directory) and text file on desktop
- [Intro to Nano](#intro-to-nano)
- [Edit Text File in Nano](#edit-text-file-in-nano) and save changes 
- [Create a Python File](#create-a-python-file)
- [Edit a Python File in Nano](#edit-a-python-file-in-nano)
- [Run a Python Program from the Terminal](#run-a-python-program-from-the-terminal)

## Raspberry Pi Setup
The first step that we take in this Linux/Cyber unit is to boot a raspberry pi linux desktop.  
[raspberrypi.org](https://raspberrypi.org) has lots of resources if you are not familiar with raspberry pis.  
It can take a few minutes to boot and setup the pis and some students will have more trouble with this than others.  
I let students know that they can change their desktop preferences in anyway they like.  This gives the students something to do while other students are getting theirs setup.  And I have found that all students like to change background images, fonts...

This is initial screen that comes up when they boot the desktop.  
![first screen](https://github.com/drewray80/linux_cyber_unit/blob/main/img/first_screen.png)

This is my desktop after I change the preferences. (I show mine to my students.)
![my preferences](/img/my_preferences.png)

[Back to Outline](#outline)
## Basic Terminal Commands
Once everyone has their pi running and are finished adjusting the preferences, I have them open a terminal window.  I spend some time explaining that the terminal how we control a computer without having to build a GUI or desktop.  And that if we access a computer remotely like a server, the terminal is the only interface that we will see.  
(We do activity for remoting into their pis using ssh, so I let them know that they will be using only the terminal very soon.)

It is important for their terminal to be sized so that it only covers half of the screen (the right half).  This lets them see directories and files appear on the desktop as they create them.  
With the terminal open, we go through a few basic commands for navigating the directories and files from the terminal.  
(If you are not familiar with linux commands, you can just search the internet for the commands that are in my pictures to find more information.) 

ls, cd <*file or dir name*>, cd, cd .. (plus any other commands that you want to demonstrate)

![basics 1](img/basics/basic1.png)

[Back to Outline](#outline)
## Create a Directory 

Then I have them navigate to their Desktop directory.  
Create a directory (*using mkdir*) on their desktop and cd into it.  
It will appear where they can see it on the desktop.  
![basics 2](img/basics/basic2.png)

Then I have them open their new directory by double clicking on the desktop folder, so they can see the effects of our terminal commands.  

![basics 3](img/basics/basic3.png)

Next, we use the *touch* command to create a text file in our directory.  
This shows them how to create a file and gives us the most basic file to edit in the nano editor.

![basics 4](img/basics/basic4.png)

They will see the text file appear in the desktop folder.  
I also have them us the *ls* command to list the items in the directory from the terminal.   
This lets them see that the new file is visiable in terminal as well. 

![basics 5](img/basics/basic5.png)

[Back to Outline](#outline)
## Intro to Nano
Using the text file that they created, I show them how to use a text editor from the terminal.  
I use Nano in my classes.  VIM is a more professional terminal editor, but for my classes I keep it simple with nano.  

First, I have them open their text file in nano.  (using *nano file_name.txt*)  
I point out that *nano* in this case is the command to run the nano program.

![nano_1](img/nano/nano1.png)

Once nano is open, I spend a lot of time explaining that we have "left the terminal". We are now in the nano editor just like opening VS Code or CodeHS Sandbox or any editor you use in class.  
I also point out things that changed on the screen: the colors/theme, the header (File, Edit...), the footer (^G Help...)
Then we edit the file by adding some text.

![nano_2](img/nano/nano2.png)

[Back to Outline](#outline)
## Edit Text File in Nano

Saving changes in nano is the most confusing aspect for new users, so I spend a lot of time on this.  

The footer of nano is basically the menu of options.  (^ strands for the control key)  
Control+G will take you to a Help page, Control+X will exit nano an take you back to the terminal...

To save our changes, we need to "write" those changes to the file. 
So we use Control+O for Write Out.

After clicking Control+O, the footer changes and asks where we want to write our changes.  
I explain to students this is similar to Save As on a windows computer. We can change the name of the file that we want to save our changes to, or if we want to save them to the current file we just press Enter.  
Just press Enter. 

![nano_3](img/nano/nano3.png)

After pressing Enter, nano lets us know how many lines were written to the file ("Wrote 2 Lines").  
Once the changes are saved ("written out" to the file), I have them open the file to see their changes from the desktop. 

![nano_4](img/nano/nano4.png)

Then, we edit the file by adding another line to the text and save using Control+O then Enter.  
After saving, we click on the text file again.  It gives us a pop up that something changed.  
We click Reload, and can see our changes.

![nano_5](img/nano/nano5.png)

[Back to Outline](#outline)
## Create a Python File
Now that the students have created and edited a text file, I have them create, edit, and run a simple python program.

First, we use touch to create the .py file.  
Then, open the file in nano.

![nano_7](img/nano/nano7.png)

[Back to Outline](#outline)
## Edit a Python File in Nano
Similar to the text file, we add lines for code then save the code using Control+O ('Write Out').  
I use very simple python code for this, just so they can see python that runs in the terminal.  
I like this example using a list and looping over it with print statements.  

![nano_8](img/nano/nano8.png)

[Back to Outline](#outline)
## Run a Python Program from the Terminal
Now that we have our saved python program, we exit nano and go back to the terminal.  
To run the python program, we use the command *python file_name*.  
(I explain that this is similar to when we use *nano file_name* to run a file using nano.)

![nano_9](img/nano/nano9.png)

When we are finished with this portion, I show them how to clear out their terminal commands to be able to start something new with a clean terminal window.  
The *clear* command removes all of the current commands and responses.

![nano_10](img/nano/nano10.png)

## History and Up Arrow
If students want to see previous commands, they can go through them one at a time using the up arrow on the keyboard.  
Also, the *history* command will show a list of all of the previous commands, so you can reference them.

![history](img/history.png)

[Back to Outline](#outline)








