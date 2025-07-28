🎯 Objective

Get the password for Bandit2, hidden in a suspiciously named file.


---

🖥️ Environment

Host: bandit.labs.overthewire.org

Port: 2220

Username: bandit1

Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If



---

🧰 Commands you’ll need

ls -al        # list all files including hidden ones
pwd           # tell me where I am, existentially and literally
cat <file>    # read the file’s contents


---

⚔️ Walkthrough – How a single dash can ruin your day

1. SSH into the box like a hacker in a B-movie:



ssh bandit1@bandit.labs.overthewire.org -p 2220

2. List all files like a curious gremlin:



ls -al

3. You see this:



-

Yeah. Just a single -. That’s not a filename. That’s a threat.

4. If you try this:



cat -

You enter the void. cat thinks you’re trying to pipe input from your keyboard (aka stdin). It patiently waits. Forever. Like Valve fans for Half-Life 3.

5. The fix? Use relative pathing magic:



cat ./-

Boom. You got the password.

Alternatively, if you want to look like a bash wizard:

cat -- -

That -- tells bash: “No more flags, everything after this is just filenames. Chill.”


---

🔑 Password for Bandit2:

aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG


---

📚 Takeaways

Files starting with - are trolls in disguise. Bash thinks they’re options.

Use ./ or -- to force bash to treat them like normal files.

Don’t trust anything. Not even filenames. Especially not filenames.



---

💀 Difficulty

Execution: 🟢 Easy

WTF Moment: 🔴 High

Terminal PTSD: 🟡 Moderate



---

> ✍️ Logged while standing on a moving bus, battery at 7%, caffeine levels critical. Still got it done.
Guerrilla learning never sleeps.




---
