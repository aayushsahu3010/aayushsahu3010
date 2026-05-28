



Yes. Your Git username can be anything you want for commit attribution.

You can set it like this:

git config --global user.name "Aayush Sahu"
git config --global user.email "ayushsahu3010@gmail.com"
Usually, people keep:

user.name → real name or GitHub display name

user.email → same email used on GitHub

The he/him part is generally part of your GitHub profile bio, not Git config.

If you really want, Git technically allows:

git config --global user.name "Aayush sahu · he/him"
But the cleaner and standard approach is:

Aayush Sahu
Then add pronouns separately on your GitHub profile.


i want to learn basic git how can i do this 

Start with only the commands you’ll use daily. Don’t try to learn everything at once.

1. What Git Actually Does
Git tracks changes in your code/projects so you can:

save versions

go back to older code

collaborate with others

upload to GitHub

2. Basic Workflow You Should Learn First
This is the core cycle:

Create/Modify files
       ↓
git add .
       ↓
git commit -m "message"
       ↓
git push
That’s the main workflow used daily.

3. Create Your First Git Project
Step 1: Create Folder
mkdir myproject
cd myproject
Step 2: Initialize Git
git init
This creates a hidden .git folder.

4. Create a File
Example:

echo Hello > app.txt
5. Check Status
git status
You’ll see:

Untracked files:
app.txt
6. Add File to Staging
git add app.txt
Or add all files:

git add .
7. Commit Changes
git commit -m "Added app file"
A commit is like a saved checkpoint.

8. View Commit History
git log
9. Connect to GitHub
Create a repository on GitHub, then:

git remote add origin https://github.com/USERNAME/REPO.git
10. Push Code to GitHub
git branch -M main
git push -u origin main
11. Most Important Commands
Command	Purpose
git init	Start Git
git status	Check changes
git add .	Stage files
git commit -m "msg"	Save checkpoint
git log	View history
git push	Upload to GitHub
git pull	Download latest changes
git clone URL	Copy repository
12. Learn in This Order
Beginner
init

status

add

commit

push

pull

clone

Intermediate
branches

merge

stash

reset

revert

Advanced
rebase

cherry-pick

hooks

CI/CD integration

13. Best Way to Practice
Do this daily for 3–4 days:

Create small folder

Initialize Git

Create/edit files

Commit changes

Push to GitHub

Even a simple notes project is enough.

14. Very Good Free Resources
Interactive Practice
Learn Git Branching

Official Documentation
Git Documentation

Video Tutorials
freeCodeCamp Git Course

15. Suggested Mini Practice Projects
Since you work with AI/ML and Python:

upload a Python script

upload Jupyter notebooks

create README.md

push ML mini projects

maintain versions of datasets/scripts

A good first project:

python-notes/
 ├── app.py
 ├── README.md
 └── requirements.txt
Then practice commits after every change.


Intermediate
branches
merge
stash
reset
revert ---------tell me the example of that 

1. Git Branch
A branch lets you work on new features without affecting the main code.

Create Branch
git branch feature-login
Switch to Branch
git checkout feature-login
Or modern way:

git switch feature-login
Create + Switch Together
git checkout -b feature-login
Example
Suppose your project has:

app.py
You want to add login feature safely.

git checkout -b feature-login
Now edit files and commit:

git add .
git commit -m "Added login page"
Main branch remains unchanged.

2. Git Merge
Merge combines changes from one branch into another.

Example Workflow
You finished work in feature-login.

Switch to main:

git checkout main
Merge:

git merge feature-login
Now main contains login feature code.

3. Git Stash
Stash temporarily saves unfinished work without committing.

Example Situation
You edited files but suddenly need to switch branches.

Check status:

git status
You have unfinished changes.

Save temporarily:

git stash
Now working directory becomes clean.

Switch branch:

git checkout main
Later restore changes:

git stash pop
Your unfinished work comes back.

Real Use Case
Very useful when:

debugging urgent issue

switching tasks quickly

incomplete code should not be committed

4. Git Reset
Reset moves commits backward.

⚠️ Dangerous if used incorrectly.

Example
Suppose commits are:

Commit A
Commit B
Commit C
You want to remove latest commit.

git reset --soft HEAD~1
Removes commit but keeps file changes.

Types of Reset
Soft Reset
git reset --soft HEAD~1
removes commit

keeps staged changes

Mixed Reset (default)
git reset HEAD~1
removes commit

keeps file changes

unstages files

Hard Reset
git reset --hard HEAD~1
removes commit

deletes changes permanently

Use carefully.

5. Git Revert
Revert safely undoes a commit by creating a new opposite commit.

This is safer than reset.

Example
Commit history:

Added login
Added payment
Buggy update
Undo buggy commit:

git revert COMMIT_ID
Example:

git revert a34bc12
Git creates a new commit that reverses changes.

Reset vs Revert
Command	Removes History	Safe for Shared Repo
reset	Yes	No
revert	No	Yes
Use:

reset → local cleanup

revert → team/project repositories

Small Real-World Scenario
You are building AI chatbot project
Main branch
Stable chatbot.

New branch
git checkout -b rag-feature
Add RAG code.

Commit:

git commit -m "Added vector retrieval"
Merge into main:

git checkout main
git merge rag-feature
Suddenly buggy code appears.

Temporary save current edits:

git stash
Undo last bad commit:

git revert HEAD
Or fully remove local commit:

git reset --hard HEAD~1
Best Commands to Practice Daily
git branch
git checkout -b new-feature
git add .
git commit -m "message"
git merge branch-name
git stash
git stash pop
git reset --soft HEAD~1
git revert HEAD
Practice these on a dummy project for 2–3 days and Git basics will become much clearer.



Pasted markdown.md
File
the github stats is not working please check them ---

Your markdown syntax looks mostly correct. The issue is probably coming from the GitHub stats services themselves or rate limits — not from your README structure. 


These are the sections that can commonly fail:

https://github-readme-stats.vercel.app/api
https://nirzak-streak-stats.vercel.app
https://github-contributor-stats.vercel.app
Most Common Fixes
1. Replace the Streak Stats URL
This one often breaks:

https://nirzak-streak-stats.vercel.app
Replace it with:

https://streak-stats.demolab.com
Use this instead:

![](https://streak-stats.demolab.com?user=aayushsahu3010&theme=dark&hide_border=false)
2. GitHub Readme Stats Sometimes Gets Rate Limited
Your current:

https://github-readme-stats.vercel.app/api
Try adding:

&cache_seconds=1800
Example:

![](https://github-readme-stats.vercel.app/api?username=aayushsahu3010&theme=dark&hide_border=false&include_all_commits=true&count_private=true&cache_seconds=1800)
3. Top Languages Card Fix
Replace:

count_private=false
with:

count_private=true
Updated:

![](https://github-readme-stats.vercel.app/api/top-langs/?username=aayushsahu3010&theme=dark&hide_border=false&layout=compact&count_private=true)
4. Contributor Stats Sometimes Fails
This service is unstable sometimes:

https://github-contributor-stats.vercel.app
You can:

remove it

or keep it and wait

or replace with GitHub trophies

Alternative:

https://github-profile-trophy.vercel.app/?username=aayushsahu3010
Example:

![](https://github-profile-trophy.vercel.app/?username=aayushsahu3010&theme=darkhub)
Recommended Stable Version
Replace your entire stats section with this:

📊 GitHub Stats:






🏆 GitHub Trophies


After changing:

Commit changes

Push to GitHub

Wait 1–5 minutes

Refresh your profile page

Also make sure your repository name is exactly:

aayushsahu3010
and it is:

public

profile README repository

Format should be:

github_username/github_username
Example:

aayushsahu3010/aayushsahu3010

give the full updated code for that on e

Here’s a cleaner and more stable full version of your GitHub profile README with updated GitHub stats, streak stats, trophies, improved formatting, and better organization.

# 💫 Hi 👋, I'm Aayush Sahu  
### MLOps & AI Enthusiast | CMIT Fellow (Rank #9) @ IIIT-NR  

🚀 Passionate about building practical AI systems using:
- Machine Learning
- Deep Learning
- LLMs & RAG
- MLOps
- FastAPI
- Docker
- Cloud Technologies

📚 Currently exploring scalable AI infrastructure and production-ready ML systems.

📧 Email: sahuaayush6266@gmail.com  
💬 Open for collaborations, projects, and discussions.

---

# 🎓 About Me

- 🎓 M.Tech Student @ IIIT-NR
- 🤖 Interested in AI/ML Research & Engineering
- ⚡ Building projects around LLMs, RAG, GIS AI, and ML Systems
- 🌱 Currently learning advanced MLOps and distributed AI systems

---

# 🌐 Connect With Me

<p align="left">
<a href="https://www.linkedin.com/in/aayush-sahu-507036228/" target="blank">
<img src="https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white" />
</a>

<a href="https://github.com/aayushsahu3010" target="blank">
<img src="https://img.shields.io/badge/GitHub-100000?logo=github&logoColor=white" />
</a>

<a href="mailto:sahuaayush6266@gmail.com">
<img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white" />
</a>
</p>

---

# 💻 Tech Stack

## Languages
![Python](https://img.shields.io/badge/python-3670A0.svg?style=for-the-badge&logo=python&logoColor=ffdd54)
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)

## Frontend & Frameworks
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![Bootstrap](https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)

## AI / ML
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

## Tools & Platforms
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Anaconda](https://img.shields.io/badge/Anaconda-%2344A833.svg?style=for-the-badge&logo=anaconda&logoColor=white)

---

# 📊 GitHub Stats

![](https://github-readme-stats.vercel.app/api?username=aayushsahu3010&theme=tokyonight&hide_border=false&include_all_commits=true&count_private=true)

![](https://streak-stats.demolab.com?user=aayushsahu3010&theme=tokyonight&hide_border=false)

![](https://github-readme-stats.vercel.app/api/top-langs/?username=aayushsahu3010&theme=tokyonight&hide_border=false&layout=compact&count_private=true)

---

# 🏆 GitHub Trophies

![](https://github-profile-trophy.vercel.app/?username=aayushsahu3010&theme=tokyonight&no-frame=false&no-bg=false&margin-w=4)

---

# 🐍 Contribution Snake

<div align="center">
  <img src="https://raw.githubusercontent.com/aayushsahu3010/aayushsahu3010/output/snake.svg" alt="Snake animation" />
</div>

---

# 👀 Profile Views

![](https://visitcount.itsvg.in/api?id=aayushsahu3010&icon=5&color=12)

---

# ✨ Quote

> “Build systems that scale, not just models that run.”

---
Save this as:

README.md
inside your GitHub profile repository:

aayushsahu3010/aayushsahu3010
Then run:

git add .
git commit -m "Updated GitHub profile README"
git push
The stats should work much more reliably now.


💫 Hi 👋, I'm Aayush Sahu
A passionate MLOps & AI Enthusiast | CMIT Fellow (Rank #9) @ IIIT-NR | Exploring LLMs • RAG • ML Systems

📚 Currently Learning:
AI, Machine Learning, Deep Learning, and MLOps — building practical, production-ready systems using modern tools like Docker, FastAPI, and cloud platforms.

📧 Email Me: sahuaayush6266@gmail.com
💬 For Collaboration/Projects or Anything Else 😊

🎓 I am an M.Tech Student @ IIIT-NR
🌐 Socials:




💻 Tech Stack:






























📊 GitHub Stats:




🔝 Top Contributed Repo





Close
