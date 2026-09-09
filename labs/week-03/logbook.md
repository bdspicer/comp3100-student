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
03
**Work Order No.:**
03
## Milestone 1
**What I did:**
1. I used the "cat pantograph.c" command to read the contents of the pantrograph program.
2. I used the "make" command to cast the program, getting "silence" from the compiler, according to the work order:
    gcc -Wall -Wextra -g -o pantograph pantograph.c
    gcc -Wall -Wextra -g -o zombie-maker zombie-maker.c
3. I ran "./pantograph echo test" to see the program fail, which output "pantograph: fork: Success," because perror is reporting the last error that failed, rather than the one that I just caused.
4. I changed "pid_t child = -1" to "pid_t child = fork()" to store the return of fork() in "child." After running "make" and "./pantograph echo test" again, the program printed 
    "pantograph: desk copied -- the copy is 3428, and it runs 'echo'
    pantograph: copy 3428 finished -- exit status 0
    pantograph: execvp: Success"
5. I added "execvp(argv[1], &argv[1]);" to the child branch, which runs if the child's copy returns "0."
6. After running "make" and "./pantograph echo test" again, the file's output read:
    pantograph: desk copied -- the copy is 4231, and it runs 'echo'
    pantograph: copy 4231 finished -- exit status 0
    test
The program is now able to execute "echo," which repeated "test."
7. When running "./pantograph false" the copy's exit status returned as "0," because status was hardcoded to "0" in the C program. I fixed this by adding the following block above "WIFEXITED"
    if (waitpid(child, &status, 0) < 0) {
        perror("pantograph: waitpid");
        return 1;
    } 
This caused the exit status for "/.pantograph false" to change to 
"1." 
The output for "make" also changed to
    make: Nothing to be done for 'all'.
8. I ran a few commands as an experiment, "./pantograph ls -l /etc/hostname," "./pantograph no-such-tool," and "./pantograph sleep 3,"
    8.1
        pantograph: desk copied -- the copy is 3783, and it runs 'ls'
        -rw-r--r-- 1 root root 16 Sep  4 13:00 /etc/hostname
        pantograph: copy 3783 finished -- exit status 0
    To my understanding, this command called "ls" with the "-l" flag specifying which pieces of information to report.
    8.2
    
        pantograph: desk copied -- the copy is 3759, and it runs 'no-such-tool'
        pantograph: execvp: No such file or directory
        pantograph: copy 3759 finished -- exit status 127
    The exit status "127" is the status for an unkown command.
    8.3 
        pantograph: desk copied -- the copy is 3770, and it runs 'sleep'
        pantograph: copy 3770 finished -- exit status 0
    The sleep comand caused the terminal to wait for 3 seconds, before successfully returning its exit status.

    
**Output or seal:**
~~~ WAX SEAL of the Guild: 28574A31 ~~~
**What it means:**
The work order says that this is the process behind every command that executes. The fork() command is called to create a child, the execvp(arg[1] and &argv[1]) is called to pass over the command, and waitpid collects the result.
## Milestone 2
**What I did:**
1. I ran "./zombie-maker" and got the output:
    zombie-maker: I am 585; my child was 590 and has already finished.
2. I then ran "ps -C zombie-maker -o pid,ppid,stat,cmds -C zombie-maker -o pid,ppid,stat,cmd" to get the pid, ppid, state, and command of the two processes involved:
    PID    PPID STAT CMD
    585     346 S    ./zombie-maker
    590     585 Z    [zombie-maker] <defunct>
3. I reran the previous command with the addition of "| tee" and a file location to write the output to a text file.
4. Next, I ran "grep -E '^(Name|State|PPid)' /proc/640/status" to print the name, state and PPid of the zombie.
5. I ran "kill 729" to terminate the parent, and the console output:
    [1]+  Terminated                 ./zombie-maker
6. Finally, I input "ps -C zombie-maker -o pid,ppid,stat,cmd" to get the following output:
    PID    PPID STAT CMD
**Output or seal:**
~~~ WAX SEAL of the Guild: FEC4E730 ~~~
**What it means:**
If the parent fails or delays to call waitpid on the child process, the uncollected result of that process will live on in the 'Z' state.
## Milestone 3
**What I did:**
1. I used the "ps -u $(id -un) -o pid,ppid,stat,etime,cmd" comman to take the census of currently running programs and their parents.
        PID    PPID STAT     ELAPSED CMD
        346     344 Ss         32:56 -bash
        416       1 Ss         32:56 /usr/lib/systemd/systemd --user
        418     416 S          32:56 (sd-pam)
        454     348 Ss+        32:55 -bash
    1049     344 S          01:27 /home/daniel/enginehouse/machinery/loom-tender
    1090     346 R+         00:00 ps -u daniel -o pid,ppid,stat,etime,cmd
2. I used the "tender=$(pgrep -x -u "$(id -un)" loom-tender" command to save loom-tender's pid.
3. I used the "pstree -p -s $tender" command to display loom-tender's parentage:
    systemd(1)───init-systemd(Ub(2)───SessionLeader(343)───Relay(346)(344)───loom-tender(1049)
4. I used the "pstree -p -s $$" command to get the tree for a command to get the parentage for that command:
    systemd(1)───init-systemd(Ub(2)───SessionLeader(343)───Relay(346)(344)───bash(346)───pstree(1138)
5. I used the "/proc/$tender/status" command to get the following output:
    Name:   loom-tender
    State:  S (sleeping)
    PPid:   344
6. I used the "tr '\0' '\n' < /proc/$tender/environ" command to "get the environment the job was handed when it started." I am not entirely sure what "environment" means in this case.
    "HOME=/home/daniel
    PATH=/usr/bin:/bin
    PWD=/home/daniel
    PATRON=E.K."
**Output or seal:**
7. I used the "printenv PATRON echo $?" to attempt to get the patron of my shell's current environment, and got the following output:
    '1'
8. I used the "head -1 ~/enginehouse/spool/loom-tender/tables.out" command to get the first line and then the first several lines of the loom-tender file:
    TABLE OF PRODUCTS -- computed by hand, entered fair, in ink
~~~ WAX SEAL of the Guild: DE502992 ~~~
**What it means:**
The parent, the creator of this loom-tender has exited, causing the base process to "adopt" it. According to the work order, this implies that someone entered the system and left before I got here, trying to cover their tracks. The only trace that they left was what appears to be a set of initials in the patron field: "PATRON=E.K"
> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. I believe that splitting the process into two with a separate fork() and execvp() command allow for more error prevention. In task one, I was able to implement execvp in an if statement that only executed if the forked copy returned '0.' The single "execute command" route would be less robust than the fork() route.
2. A zombie holds the result of its process, along with its process' pid, the parent pid, the status, and the command that created it. To my understanding, an orphan holds its name, state, pid, and ppid, as well as its parent tree. I am unsure of why the zombie is the one that can bring a machine down. My best guess is that zombies can overpopulate and drain valuable resources, and can be quite hard to get rid of.

## Sources and help

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

Dr. Faith helped me with some confusion with pulling from the GitHub repository.

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent

Roughly how long this took, start to finish: 3 hours
*No wrong answer — this just helps calibrate future work orders.*
