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
| 4 |  |  |  |

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


*Tip: if two weeks' findings seem to point the same direction, say so
in a note — connecting your own dots across weeks is exactly the
skill this ledger is for.*
