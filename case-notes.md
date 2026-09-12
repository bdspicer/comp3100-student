# Case Notes

*Honourable Guild of Enginewrights — Ex Vapore, Ordo*

Copy this into your repo root as `case-notes.md` (or wherever your
work order says) and keep it running all semester. Add one row every
week for anything odd you notice while you work — even if you're not
sure it matters yet. Small, plain notes are more useful later than
you'd expect.

The skill this builds is noticing; explaining comes later, sometimes
weeks later. A half-formed note beats a tidy one you meant to write
and never did.

## The ledger

| Week | What I found | Where/how | What I think it means |
|---|---|---|---|
| 1 | During Task 2, I found a punch card, which was notably lacking the "registered" stamp. | I found it in the form of a .txt file in my inbox, using the "ls -la" command. I accessed its contents with the "cat" command. | Based on the information in the work order, I would guess that the loom didn't accept the punch card. My guess is that this has some connection to the disgruntled human computers. |
| 1 | During Task 3, when I tried to access the manual page for write(1), I got the response: ""No manual entry for write in section 1."" | I used the command "man 1 write," a command that worked for my other classmates, multiple times, to no avail. | I am currently unsure of what this means or why it happened. |
| 2 | Last Line with Date: 2 May 1851 — 5 hrs computed by hand, uncompensated. — your diligent servant Closing line: 12 June — 6 hrs computed by hand, uncompensated. — your diligent servant | /home/daniel/.ledger-annex | I think the Engine still utilizes the human computers in some way, in Mechanical Turk fashion, and that whichever of these employees remain aren't being fully compensated for their work. |
| 3 | "TABLE OF PRODUCTS -- computed by hand, entered fair, in ink" | "head -1 ~/enginehouse/spool/loom-tender/tables.out" | I am not sure what this could mean, apart from the fact that someone can get in and out of the system at will. |
| 4 | #                                        By order of ███  | I used the "cat ~/enginehouse/machinery/amendment-314.sh" command | There is someone human (or formerly human?) who used to work as a computer pulling strings behind the scenes. |
      14 15 * * * $HOME/enginehouse/machinery/amendment-314.sh # Dispatch Board Amendment No. 314 — by order of ███  | I used the "crontab -l" command  | This person seems to want things to go back to the way they were before, considering the way their language glorifies the methods of the past: "in committee assembled, registered at no loom -- and entered upon the Board's books by hand." The regular nature of these disruptions feels important. It's as if they wanted us to investigate it. |

Add more rows as the weeks go on. Keep entries short — a sentence or
two per column is plenty, and a note that turns out to be nothing
costs you nothing.

- **What I found** — the plain fact. Just what you saw.
- **Where/how** — the file, command, or tool that showed it to you.
- **What I think it means** — your own read on it. Guesses are fine;
  label them as guesses if you're unsure, and "no idea yet" is a
  perfectly legitimate entry.

## Current suspicions
*Free-write space. What's your running theory? What doesn't add up yet? Revise this section any week — nobody's grading you on being right early, only on citing your own notes later.*
Week 01:
  It seems that there is more to the story of the former employees of the computing room. The incorrigible note announcing the decision to deny their pensions and the mysterious punch card make two loose ends relating to these workers.
Week 02:
  It seems that one or more of these human employees are still here in some way, even if that means that the Engine is copying a note left by one of them. The fact that this is unregistered makes me think that one of them may have some sort of administrative access to the Engine.
Week 03:
  To have the parentage the way it was, I believe that someone had to have killed the parent process. The patron of this card is "PATRON=E.K." My shell doesn't set a "patron" variable (as per the printenv PATRON command printing '1'). There's also the table of products in the loom-tender: "
    TABLE OF PRODUCTS -- computed by hand, entered fair, in ink 
      "17 x   28 =       476   checked by casting out nines -- agrees"
  This is not the output of a computer. A human computer has learned how to infiltrate the system, but hasn't covered their tracks perfectly.
  Week 04:
  What I found: 
   DISPATCH BOARD  --  AMENDMENT  No. 314
#
#   Being an AMENDMENT to the STANDING ORDERS OF THE DISPATCH BOARD,
#   drafted, moved, and carried in the form prescribed of old --
#   on paper, in committee assembled, registered at no loom --
#   and entered upon the Board's books by hand.
#
#   WHEREAS the Standing Orders provide that the Board shall
#      dispatch every job in fair rotation, each according to its
#      courtesy; and
#
#   WHEREAS a PUBLIC DEMONSTRATION is held daily at three o'clock
#      in the Engine gallery, before schoolchildren and aldermen;
#
#   BE IT AMENDED, that at FOURTEEN MINUTES PAST THREE o'clock
#      there be dispatched certain URGENT WORKS, in number twice
#      the count of engines upon the floor, owing courtesy to no
#      other job whatsoever, to hold every engine wholly;
#
#   AND FURTHER, that the said works shall stand down of their own
#      accord upon the elapse of NINETY SECONDS, leaving no paper
#      upon the Board;
#
#   AND FURTHER, that this Amendment renew itself daily, at the
#      hour and minute appointed, until it be struck out.
#
#              Moved, seconded, and carried without division.
#                                        By order of ███
    1.The paper reads like committee minutes — WHEREAS, BE IT AMENDED, moved, seconded, and carried — drafted with real fluency, on a system that keeps its standing orders in one-line table rows. What kind of hand writes an amendment in that form, and writes it well? What would it take to fake that fluency?
      I am not entirely sure what response this question is fishing for, but, asince the amendment says "entered upon the Board's books by hand," it seems like the entity doing this has some level of humanity, and wants us to know as much. The language is written in a format and a style that suits an institution made up by people rather than a machine. This week was unlike last week; they aren't trying to hide from us anymore.
    2. Look at what the amendment was careful about. Ninety seconds and self-sweeping. A one-line strike-out restores everything. The Demonstration was humiliated; no ledger, no loom, no scrap of work was harmed. If you wanted to hurt this house, is this how you would do it? If not — what is this?
      If I wanted to hurt the house, I would have caused the system to switch to FIFO, or used crontab -r to wreak havoc. The entity doing this has some level of care for the system: "". This seems like an attempt to get our attention. 



*Tip: if two weeks' findings seem to point the same direction, say so
in a note — connecting your own dots across weeks is exactly the
skill this ledger is for.*
