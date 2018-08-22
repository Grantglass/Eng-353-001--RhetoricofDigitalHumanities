
---

DH Box is a cloud computing platform for the digital humanities. _A_ DH Box is a single cloud computing workstation. This just means it's a computer that lives in the Internet, rather than on your laptop. Everything you can do on a DH Box you can also do on your own computer. But if you used your own computer, it might take a while to set up all the software just right. DH Box already has all the software you need, and it's all configured correctly. This allows you to get right to work, without spending hours installing and configuring software.


## Working with Files

You can get files in and out of a DH Box in a number of ways. Let's start by using the file manager. Download a plain text file (a file with the .txt) from the Internet. As an example, we can use the Project Gutenberg edition of Alice's Adventures in Wonderland, which you can get from [gutenberg.org/files/11/11-0.txt](http://www.gutenberg.org/files/11/11-0.txt). Go to that website, and save the file to your computer. This can usually be done by choosing "save as" from your web browser's File menu, or by right-clicking on the page and choosing "save page as." Now, in DH Box, go to your DH Box's File Manager tab, and click the "upload" button. Choose the file you just downloaded, which should be called 11-0.txt. Now you have a text file in your DH Box, saved to the `/home` directory. Let's do things with it. 

Go to the "command line" tab and log in using your username and password. Note that you won't see any text appear on the screen as you type in your password. 

First, see what directory you're in by typing the command `pwd` and pressing enter (`pwd` stands for "print working directory"). It should say something like `/home/username`, where "username" is your DH Box user name. Since I'm using the demonstration DH Box, for instance, I see `/home/demonstration`.

![](images/tour-pwd.png)

Since we saved our file to the `/home` directory, and not `/home/demonstration`, we'll have to change into to the `/home` directory to find our file. Type `cd /home` and press enter. (The command `cd` stands for "change directory.")

![](images/tour-cd-home.png)

Now let's verify what directory we're in. Type the command `pwd` and press enter. You should see it display `/home`. Now we're in our `/home` directory, where we saved our text file. Let's see if the text file is there. Type `ls` and press enter. You should see it show the name of the file you just uploaded, `11-0.txt`, and the `demonstration` directory, or whatever your username is. 

Now we can do things with this text file. For example, let's get it to display the first few lines of the file. Type the command `head 11-0.txt`, and press enter. (From now on, I'm going to just say "run the command.")

![](images/tour-head.png)

There's a lot of Project Gutenberg license material there. We won't be needing that, so let's open a text editor and take it out. Go to the Brackets tab of your DH Box. Brackets is just a text editor program. There, in the File menu, choose "open." Select the file `11-0.txt`, and click the button "open." Now select all the text up to and including `*** START OF THIS PROJECT GUTENBERG EBOOK...` and delete it by pressing your backspace or delete key. You can also remove the license material from the end of the book in the same way. Save your changes by selecting "save" from the file menu. 

![](images/tour-brackets.png)

Now let's go back to the command line and try a few more things. Click the "command line" tab on your DH Box. How many words are in _Alice's Adventures in Wonderland_? To find out, run the command `wc -w 11-0.txt`. 

![](images/tour-wc.png)

We can also work with our text file using Python. Click the "Jupyter Notebooks" tab on your DH Box. Click the "new" button and select "Python 3." You should now see a box labeled `In [ ]:`. Click in the box next to that colon. Let's verify what directory we're in here. Type `%pwd`, then press Shift + Enter (hold down Shift and press Enter or Return). It should say `/home`. 

![](images/tour-python-pwd.png)

Let's make sure our file is there. In a new cell, type `%ls` and press Shift+Enter. You should see our file, `11-0.txt` there.

![](images/tour-python-ls.png) 

Let's read in our file and do some things with it. In a new cell, enter the command `alice = open("11-0.txt").read()`, and run it using Shift+Enter. In a new cell, enter and run the command `print(alice[:150])`. This will print the first 150 characters of the book: 

![](images/tour-python-alice.png)

Now you're ready to start analyzing the text! Fun digital humanities projects, here we come. For more on text analyses, see my tutorial
[text-analysis-tutorial.md](https://github.com/DH-Box/docs/blob/master/text-analysis-tutorial.md) in [the DH Box documentation repository](https://github.com/DH-Box/docs). 


## Further Resources

To learn more about the command line there are tons of introductory tutorials online. Just search for "command line tutorial" or visit one of these websites:

 - https://programminghistorian.org/lessons/intro-to-bash
 - https://tutorial.djangogirls.org/en/intro_to_command_line/

There are even interactive tutorials at sites like codecademy.com, which also has free interactive Python tutorials. To learn more about Python, try searching for "python tutorial" on YouTube, or visit one of these sites: 

- [Python lessons on Programming Historian](https://programminghistorian.org/en/lessons/?topic=python)
- [Introduction to Python](http://introtopython.org/)