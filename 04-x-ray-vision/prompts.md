# 04 · X-Ray Vision — prompts

**Context:** You joined Rook two weeks ago as PM on Dispatch.
Release 4.2 shipped on 12 August, just before you arrived, and
landed badly. Last session the numbers showed you what happened: a
ping used to wait ninety seconds and now it waits sixty, people
missed pings they used to catch, and missing one counts the same as
turning one down — so four responders stopped hearing from us
altogether.

At the end of the session, ask Claude Code to save the prompts you
wrote yourself below — not the starter prompt. The closing slide has
the exact prompt to paste. By Module 6 this file is a prompt library
built from your own questions.

---

### 1.

Open the folder 00-rook/code/dispatch-routing/. This is the part of our software that decides who gets asked to take a job. I have never read code before and I am not going to start now. Walk me through what happens from the moment something goes wrong somewhere to the moment a responder's phone buzzes, in plain English, no jargon. Then tell me which file each step lives in.

### 2.

Has anything in this code changed recently? Walk me through what's different, and why it would matter to a responder.

### 3.

did the change to who gets asked first apply to responders who'd already been turning jobs down, or just new ones?

### 4.

Which file has last session's numbers in it?

### 5.

Find me the part of this code that takes points off somebody when they miss a ping or turn one down. Show it to me and explain it in plain English. Then find me every single thing in this code that puts points back on.

### 6.

The reduction in time from 90 to 60 secs , where is that in the code?

### 7.

omebody has been quiet for a month. Walk me through, step by step, exactly what would have to happen for them to start getting work again.
