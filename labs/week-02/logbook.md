# Engineer's Logbook

*Honourable Guild of Enginewrights — Ex Vapore, Ordo*

Copy this into your week's folder as `logbook.md` and fill it in as you
work. Paste your wax seals where marked — that's how a milestone gets
marked done.

Write it the way you'd explain the week to a classmate who missed it:
plain sentences, no polish. An honest half-answer under "what it
means" — *I got the seal but I'm still fuzzy on why the second run
differed* — beats a confident sentence you don't believe, and it tells
me where to start when you bring it to studio.

**Name:**
Daniel Spicer
**Week:**
02
**Work Order No.:**
02
## Milestone 1
**What I did:**
1. I viewed hello-brassbridge.c with the "cat" command.
2. I then compiled the command with gcc by using the "make" command, which gave me a few faults and warnings within the c code.
3. The first fault was that the program implicitly declared the strlen function without explicitly asking for it up front. I addressed this by adding "include string.h" as suggested by ASan.
4. The second fault was the syntax error in "(if total = 30)." This was written as an assignment statement rather than the intended equality comparison.
5. The Third fault was a stack-buffer-overflow in one of the for loops.
6. The fourth fault was the uninitialized "total" variable, something that only valgrind would call out.
7. I fixed the errors as specificed in the error messages, and ran "./hello-brassbridge" which built the program with ASan, which watched my arrays for any issues. It found a stack buffer overflow. One of my for loops was writing past the end of the array.
8. I fixed the for loop and ran the program with ASan again, confirming that my for loop was staying within bounds.
9. I ran the program with valgrind and discovered that one of my variables--the tally variable--wasn't initialized properly and was thus being assigned a "garbage" variable.
10. I fixed this by initializing the variable at the beginning of the program, and ran it with valgrind again to test me fix.
11. I reran the program with ASan to confirm its output, and claimed the seal.
**Output or seal:**
~~~ WAX SEAL of the Guild: 02B4DE0C ~~~
**What it means:**
1. As a developer, I will often be handed programs with errors in them, and it is good practice to check them for warnings and errors before doing anything else with them.
2. Running the program separately through ASan and valgrind can help me isolate certain types of errors or warnings that the compiler may not clock.
## Milestone 2
**What I did:**
1. I input "strace -c ls" to list the system calls made to list the files in a directory.
2. I used "~/enginehouse/bin/card-reader" to view the card reader.
3. I then added "strace -c" to the same command "strace -c ~/enginehouse/bin/card-reader" to list the requests made by this command.
4. I used the "strace -e trace=openat,write ~/enginehouse/bin/card-reader" command, strace with no -c, to view a certain list of calls and their arguments. Something strange was contained with in these calls, a file, "/home/daniel/.ledger-annex", that the work order assigned a strange amount of significance to. The tool wrote to it, and the output reads "12 June \342\200\224 6 hrs computed by ha"...,"
5. When I tried to claim the seal, I got an error that read: "make: *** [Makefile:18: m2] Error 1" I remembered Dominic having a similar problem, so I asked him how he fixed it, and he told me that I was getting this error because I hadn't saved my answers.txt file. He was correct.
**Output or seal:**
~~~ WAX SEAL of the Guild: D6B5301A ~~~
**What it means:**
1. The "strace" command can fib. 
2. Using "strace" without "-c" to view everything, including each calls' arguments.
3. I can specify when calling "strace" to get information about a particular call.
## Milestone 3 
**What I did:**
1. I used the "ls ~" command and the "ls -a ~" command to view every file within the current directory, including configuration files, in the latter's case.
2. I used the "cat" command to view the contents of ".ledger-annex."
3. I used the "wc -l" command to display the number of lines in ".ledger-annex"
4. I used the "~/enginehouse/bin/card-reader" command to input another card.
5. I used the "tail -3 ~/.ledger-annex" command to view the last three lines of the ".ledger-annex" file.
**Output or seal:**
 ~~~ WAX SEAL of the Guild: F7974ACA ~~~
**What it means:**
1. I can use "tail [number]" to view the last [number] lines of a file.
2.The system-call record is more trustworthy than a program's printed output. The program can print whenever and whatever it wants,
but it has to speak to the kernel to do anything behind the scenes.
> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. The card-reader's own output claimed all was in order while its system-call record showed an unannounced write. In two or three sentences: why is the kernel's record the authoritative one? Use user mode and kernel mode the way zyBooks 1.2 does — who runs in which mode, and who is allowed to touch the hardware.

The kernel's record is the authoritative one because no program can alter any component without first asking the kernel. When interfacing with a program, the CPU is in user mode, and when the program sends a request to the kernel, the CPU switches to kernel mode, allowing it to do things like writing to files or arranging memory. Because of this system, we know that, if anything happened behind the scenes, the kernel was involved, and it keeps the score. 

2. Four faults, three watchmen: the compiler caught two, ASan caught one at runtime, valgrind caught one more. Why do you suppose C needs all three, when the languages you knew before catch most of this in one place? One honest paragraph — "because C trusts the programmer" is a fine place to start, if you say what that trust costs and what it buys.

C trusts the programmer. That trust allows C programs to be especially robust, ignoring certain faults and running. This comes at the cost of information in the form of valuable debugging information, making tools like ASan and valgrind necessary.
## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

Dominic helped me when my "make" command didn't work properly. He advised me to move from the terminal in Visual Studio Code to Windows Powershell, which worked.
Dominic also helped me when my "make -C check m2" gave me an error--I just had to save my answer.txt file.

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent

Roughly how long this took, start to finish: 2.5 hours
*No wrong answer — this just helps calibrate future work orders.*
