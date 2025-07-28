## *Objective*  
*Find the password to Bandit1*

---

## *Environment & Access*  
1. **Host:**  *bandit.labs.overthewire.org*  
2. **Port:**  *2220*  
3. **Login:** *bandit0*  
4. **Password:** *provided on start*

---

## *Useful Commands*
```bash
ls -al    # list all files (including hidden)
pwd       # print working directory
cat       # display contents of a file


---

Walkthrough

1. Connect using SSH:
ssh bandit0@bandit.labs.overthewire.org -p 2220


2. List the contents of the home directory:
ls -la


3. Display its content:
cat readme
(Yes. Just read it. That's literally the first flag. You expected more? 😏)


4. Copy the password and save it in your own notes
(Build the habit of saving flags/hashes/passwords — it will save you a lot of frustration later.)




---

Password/Flag

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If


---

Notes / Takeaways

1. Hints under the challenge description are useful – but don't rely on them like on your ex. Trust, but verify.


2. Reading and using documentation, man pages and practicing command combos – will accelerate your growth.


3. Commit to small wins – even reading a file like this is one step closer to breaking the system (legally 😈)




---

✍️ Logged in guerrilla-mode from a mobile terminal. No excuses, only shell commands.

---
