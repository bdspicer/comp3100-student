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
04
**Work Order No.:**
04
## Milestone 1
**What I did:**
1. I used the "cat starter /loom-job.sh" command to read the loom-job program.
2. In another terminal, I started the north and south loom programs with the following two commands: 
    "nice -n 19 bash starter/loom-job.sh north &"
    "nice -n 19 bash starter/loom-job.sh south &"
3. I used the "top" command to view the current processes.
    "Courtesy is not a brake. On a quiet floor, courtesy costs nothing: nice settles who waits when jobs compete, and nobody is competing yet. "
4. I added the rates of the north and south loom jobs to the answers.txt text file.
**Output or seal:**
~~~ WAX SEAL of the Guild: 8FCFAF44 ~~~
**What it means:**
This task showed me how processes are meant to share the CPU under ideal conditions. I also learned about the top command, the menu that it brings up, and the keys to navigate through it (1, c, %, and q). When there isn't competition, tasks with high courtesy do not have to yield to anything.
## Milestone 2
1. I used the "bash report-for-duty.sh --drill" command  to start the drill, which simulates the stuter that has been happening at 3:14.
2. I grabbed the pid of one of the loom's jobs from the first terminal during the drill and inserted it into the "ps -o pid,ppid,ni,args -p 7070" command:
    PID    PPID  NI COMMAND
   7070    7037   0 sh -c while :; do :; done amendment-314-burner
3. I did the same, but this I added the ppid of the process to the command:
PID    PPID  NI COMMAND
   7464     352   0 /bin/sh /home/daniel/enginehouse/machinery/amendment-314.sh
4. This gave me the path to the shell script causing the stuttering. I ran this command to read it: "cat ~/enginehouse/machinery/amendment-314.sh"
5. I used the crontab -l command to see the scheduled command, getting this output:
    14 15 * * * $HOME/enginehouse/machinery/amendment-314.sh # Dispatch Board Amendment No. 314 — by order of ███
6. I used the "crontab -l | grep -v 'Amendment No. 314' | crontab -" command to remove the script from the "book.".\
7. I reran the drill, used the "pgrep -f amendment-314-burner" to list the pids runnning, then "renice -n 19 -p $(pgrep -f amendment-314-burner)" to equalize the courtesy between the tasks, preventing the "nicer" loom tasks from standing down and starving.
**Output or seal:**
 ~~~ WAX SEAL of the Guild: B7D13C28 ~~~
**What it means:**
You can use the "top" command to view the main tasks in question. You can also use the '1,' 'c,' and 'q' keys to modify what top shows. Courtesy can be changed while tasks are running. It is important not to have disproportionate courtesy amounts. An easy way to find the source of a sneaky script is to use the "ps -o pid, ppid, -p (pid)" command.
## Milestone 3
**What I did:**
1.
2."sudo chrt --fifo 50 sh -c 'chrt -p $$; while :; do :; done'"

3. "ps -o pid,cls,rtprio,ni,comm -p 23968"
    PID CLS RTPRIO  NI COMMAND
  23968  FF     50   - sh
4. "bash starter/loom-job.sh reference"
5. "systemd-run --user --scope -p CPUQuota=20% bash starter/loom-job.sh governed"
**Output or seal:**
  ~~~ WAX SEAL of the Guild: 23AC5925 ~~~
**What it means:**

> Fewer or more milestones this week? Copy a block above as needed.

## Reflection

1. I would keep all courtesy equal on the loom process, to prevent any from starving. I would not use the FIFO lever on the loom process during the demonstration; it seems too risky. I would use the governor on the loom process. If it opens within a new context and reserves a certain amount of the engine, it should protect it from the type of interference that was occurring at 3:14. Of course, using the governor would slow down the loom, but a slower pace would be worth the safety.
2. The scheduler was still promising the loom a certain amount of resources if they were to open up. The courtesy only makes the loom step aside because other, more demanding processes were constantly in the mix. Courtesy 19 is the right setting for a job that isn't vital and one that I am willing to let in last, assuming the others aren't too demanding or long-winded.

## Sources and help

None

Anyone or anything that helped you this week — a classmate, a man page,
a Stack Overflow answer, an AI assistant. One line each: who or what,
and what you used it for. This is **not graded and never costs points**;
it is the habit professional engineers keep, and the syllabus asks for
it under *Academic integrity* and *Use of AI tools*.

- *(example)* Worked through the `fork` ordering with Sam in studio.
- *(example)* Used an AI assistant to explain what `EAGAIN` means in the trace.

*Nothing to report? Write "None" — that's a perfectly normal week.*

## Time spent

Roughly how long this took, start to finish: 2.5 hours
*No wrong answer — this just helps calibrate future work orders.*
