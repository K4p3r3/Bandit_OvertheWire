



Bandit Level 0
Level Goal

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

Commands you may need to solve this level

ssh
Helpful Reading Material

    Secure Shell (SSH) on Wikipedia
    How to use SSH on wikiHow

----------------------------------------------------------------
----------------------------------------------------------------
Solution:
----------------------------------------------
This level is the starting point of the Bandit wargame

I'm using a linux system so the instructions in the terminal are linux based, but you can solve theses challenges using any platform.
Step1#: Launch your terminal
Step2#: Type "ssh -p 2220 bandit0@bandit.labs.overthewire.org"
Step3#: Type the password "bandit0" to gain acces to the other terminal
------------------
If you did everything well you get a result as below;



Bandit Level 0 → Level 1

Level Goal

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

Commands you may need to solve this level

ls, cd, cat, file, du, find

-------------------------
Solution:
-------------------------
This level is a short one that is meant to teach about terminal commands
In the level after gaining access to bandit0, you list using "ls" command to show the files
in that working directory then view the content of the file using "cat" command as below;



Got it! 拾拾 Thats our next level password:


Bandit Level 1 → Level 2

Level Goal

The password for the next level is stored in a file called - located in the home directory

Commands you may need to solve this level

ls, cd, cat, file, du, find
Helpful Reading Material

    Google Search for “dashed filename”
    Advanced Bash-scripting Guide - Chapter 3 - Special Characters
--------------------------------------------------------------------------------
Solution:

On the bandit website it says that the next password is saved in a file named -. This means we are dealing with dashed filenames as stated in the hints. When I logged into the account and ran "ls" I saw the file. I then ran "cat <-" and I saw that the password is: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9. In order to read files that start with a dash, you have to redirect them to stdin with the < operator.




Bandit Level 2 → Level 3
Level Goal

The password for the next level is stored in a file called spaces in this filename located in the home directory

Commands you may need to solve this level

ls, cd, cat, file, du, find
Helpful Reading Material

    Google Search for “spaces in filename”
------------------------------------------------------------------------------------
Solution:

The password for the next user is stored in a file called spaces in this filename. I ran " cat "spaces in this filename" " and received the next password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK. In order to read files with spaces in the name you have to put the file name in quotation marks or back slashes in between words.




Bandit Level 3 → Level 4
Level Goal

The password for the next level is stored in a hidden file in the inhere directory.

Commands you may need to solve this level


ls, cd, cat, file, du, find

Solution:

The password is stored in a hidden file in the inhere directory. I ran "ls" to see what files and directories there are and then I ran "cd" to move into the inhere folder. Then I ran "ls -la" to see all of the files including the hidden ones. All hidden files and folders in linux are stored with a dot in front of their name. The hidden file is named .hidden and after running "cat .hidden" I saw that the next password is pIwrPrtPN36QITSp3EQaw936yaFoFgAB.





Bandit Level 4 → Level 5

Level Goal

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

Commands you may need to solve this level

ls, cd, cat, file, du, find
--------------------------------------------------------------------------------
Solution:

Step1#: View the files that are present in the current working directory using the ls command
Step2#: Move into the inhere/ directory. This can be done using the cd command
Step3#: View files that are in the directory using the ls command
Step4#: We know we have to find file who’s content is in Human Readable format. This check can be performed using the file command. File command returns the type of data that is found in the file
Step5#: View the content of -file07 file using the cat command

NOTE: The * here means search all files in the directory. For more information on file globbing refer the attached reference resources

See below commands in action:


Got It!拾拾

Bandit Level 5 → Level 6
Level Goal

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable

Commands you may need to solve this level

ls, cd, cat, file, du, find
------------------------------------
Solution:

View the files that are present in the current working directory using ‘ls’ command

Move into the inhere/ directory using the cd command and list the contents using ls.

To search for the file that we require using the properties that are specified in the question we can make use of the find command.

(Refer man pages to read more on the various options that can be used along with the find command)-

Where:
    . : Search the current working directory only
    -type f : Look for files only (Exclude Directories)
    -size 1033c : Look for files that are exactly 1033 bytes in size (Find uses “c” to represent bytes)
    -not -executable : Find only non executable files
    -exec file {} + : Execute the file command on all the results returns by find

NB:  {} is an placeholder for the location where the names of the files found by find is going to be substituted. The “+” sign is used to terminate the statement

We then cat the file found using the command and get the password for the next level.


============================================================
Yeeey拾拾拾..We made it this far拾

This is the password for our next level!!

NOW YOU USE THE PASSWORD TO LOGIN TO THE NEXT LEVEL.
