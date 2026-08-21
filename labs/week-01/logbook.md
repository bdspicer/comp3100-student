# Engineer's Logbook

*Honourable Guild of Enginewrights — Ex Vapore, Ordo*

Write it the way you'd explain the week to a classmate who missed it:
plain sentences, no polish. An honest half-answer under "what it
means" — *I got the seal but I'm still fuzzy on why the second run
differed* — beats a confident sentence you don't believe, and it tells
me where to start when you bring it to studio.

**Name:**
Daniel Spicer
**Week:**
01
**Work Order No.:**
1
## Milestone 1
**What I did:**
1. I used the "uname -a" command to get my kernel to identify itself as microsoft-standard-WSL2.
2. I used the "strace" command to get my file listing, and the table of calls made.
3. I used the "--version" command to get my C compiler to identify itself and its version.
4. I used the "man 2 read" command to open the System Calls Manual Page.
5. When I input the "make -C check m1" command to claim the seal, I ran into an error, and Github Copilot (correctly) advised me to input "sudo apt install make" to gain access to the command.

**Output or seal:**
 ~~~ WAX SEAL of the Guild: 2316EEC1 ~~~

**What it means:**
My WSL environment is fully installed and working as intended. The kernel is identifying itself correctly, the strace table looks as it should, my C compiler is accessible and appropriate, and the manual is accessible.
## Milestone 2
**What I did:**
1. I used the "ls -la" command to list the directories in my workspace.
2. I used the "ls" command to check the /spool directory in my workspace. The terminal said nothing, showing that the directory was empty.
3. I used the "ls" command on the /inbox directory and found two text files.
4. I used the "file" command to the inbox directory, which informed me on the contents of the two files.
5. I used the "cat" command to read the contents of both text files.
6. One of the files in my inbox was a punchcard with twelve rows.

**Output or seal:**
~~~ WAX SEAL of the Guild: 9D6B90F5 ~~~

**What it means:**
The terminal provides various ways to examine files, including "ls" (list), "file" (reveals the content type of the files in a directory), and "cat" (prints the specified file in the terminal).
There was a punchcard in my inbox, which will likely become important later in the story.
## Milestone 3

**What I did:**
1. I used the "whatis write" command to access a definition of the "write" command.
2. I used the "man 1 write" to access page on write(1). In my case, for unkown reasons, my terminal replied with "No manual entry for write in section 1."
3. I used the "man 2 write" command to access the page on write(2). I had no issues accessing this page.
4. I used the "man 1 crontab" command to pull up the page on the crontab program.
5. I used the "man -k clock" command to list every page that mentions the word "clock."

**Output or seal:**
  ~~~ WAX SEAL of the Guild: CB7D629D ~~~

**What it means:**
The "write" in section 1 and the "write" in section 2 have an important distinction; write(1) is for sending notes between users, and write(2) asks the kernel to print.
Crontab is a program that can install, deinstall, or list the tables running the Vixie Cron daemon.
I can search the manual for certain keywords with "man -k keyword."

## Reflection

1. In two or three sentences: what does an operating system actually do for a program like ls? You watched it happen — the strace table in Task 1 is ls asking the OS for things, one row at a time. (zyBooks 1.1 vocabulary welcome but not required.)

  An operating system enables programs like "ls" to safely and efficiently interface with the hardware. The strace table shows how the operating system takes a series of tasks and abstracts them, packaging them into what appears and behaves as one or two simple, intuitive tasks for the user.

2. The same name, write, means a chat command in section 1 and a kernel call in section 2. Why is a sectioned manual a sensible design — and when this week did the section number save you (or cost you) time?

  To my understanding, the benefit of the sectioned manual is that it prevents the amount of commands from becoming overwhelming. Due to the relative simplicity of this work order, the manual numbers did not cost or save me any significant amount of time (apart from the issues that I had with write(1), but those are not meant to be part of the project).

## Sources and help
Dominic Huff helped me set up my terminal and my WSL environment.
Github Copilot gave me the command that I needed to install "make," which enabled me to claim the first seal. 

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent
This work order took roughly three hours to complete.
