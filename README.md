# Git & GitHub – Learn With Me

Hey 👋

I learned Git & GitHub by watching some YouTube courses, reading a handbook, and practicing on a dummy project. This repo has everything I used — sharing it so you don't have to search around like I did.

Just clone it, read, practice, done.

---

## Folder Structure

```
Git-GitHub-Learning-Repo/
│
├── Resources/
│   ├── Git & GitHub Handbook.pdf
│   ├── Git Commands Cheatsheet.pdf
│   └── SSH-Key-Screenshots/
│
├── COMMANDS.md      → simple commands + when to use them
├── Index.html       → sample file to practice on
├── Index.css
└── README.md
```

`Index.html` / `Index.css` are just dummy files. Use them (or your own) to practice `git add`, `commit`, `push`, branching etc. without fear of breaking anything.

---

## Quick basics (in case you're totally new)

- **Git** = a tool on your computer that saves versions of your code. Example: like Ctrl+Z, but for your whole project, forever.
- **GitHub** = a website where you store your Git projects online. Example: think of it as Google Drive, but for code.
- **Repository (repo)** = a project folder that Git is tracking. Example: your `my-website` folder becomes a repo after `git init`.
- **Commit** = a saved checkpoint of your code with a message. Example: "added login page" is a commit.
- **Staging area** = a waiting room before a commit. Example: `git add file.js` puts it in the waiting room, `git commit` saves it for real.
- **Branch** = a separate copy of your code to try things safely. Example: `feature/login` branch to build login without touching main.
- **Main/Master branch** = the default, stable branch of your project. Example: this is the version you'd actually deploy.
- **Clone** = downloading a full copy of a GitHub repo to your computer. Example: `git clone <url>`.
- **Push** = sending your saved commits to GitHub. Example: after committing locally, `git push` uploads it online.
- **Pull** = downloading the latest changes from GitHub to your computer. Example: teammate added code, you `git pull` to get it.
- **Merge** = combining one branch's changes into another. Example: merging `feature/login` into `main` once it's done.
- **Merge Conflict** = when Git can't decide whose changes to keep because both touched the same line. Example: you and a teammate both edited line 10 differently.
- **Clone vs Fork** = clone copies to your computer, fork copies someone else's repo to your own GitHub account. Example: fork an open-source repo, then clone your fork.
- **Pull Request (PR)** = asking someone to review and merge your changes into their repo. Example: you fix a bug in an open-source project and open a PR.
- **.gitignore** = a file that tells Git which files to skip. Example: adding `.env` here so your passwords never get uploaded.
- **Stash** = temporarily saving unfinished work without committing it. Example: urgent bug fix needed, so you `git stash` your half-done feature first.
- **Remote** = the online version of your repo (usually on GitHub). Example: `origin` is the default name for your remote.
- **SSH Key** = a secure way to connect to GitHub without typing your password every time. Example: set up once, then just `git push` works directly.

That's basically 80% of what you need to know to start.

---

## Honest advice

You don't need to watch hours of tutorials to learn this.

Just open the **Handbook** in the Resources folder, and while reading, type out every command yourself. Make a dummy folder, break it, fix it. That's it. Do this for 2-3 days seriously and you'll know more than most people who only watch videos and forget it the next day.

If you still prefer watching first, that's fine too — here are the exact courses I watched:

1. CodeWithHarry — https://youtu.be/AB3J8ufDYHQ
2. Apna College — https://youtu.be/Ez8F0nW6S-w
3. Kunal Kushwaha — https://youtu.be/apGV9Kg7ics

Pick one, that's enough.

---

## Credit

Handbook & Cheatsheet made by **CodeWithHarry** — I'm just sharing them here, all credit to him.
Course link: https://youtu.be/AB3J8ufDYHQ

SSH screenshots show how to generate an SSH key and add it to GitHub, so you can push/pull without typing your password every time.

---

## How to practice

1. Clone the repo
2. Read handbook chapter by chapter
3. On the practice files, try:
   - add → commit → push
   - make a branch, merge it back
   - create a merge conflict on purpose, then fix it
   - try stash, tags, rebase once you're comfortable

Once you can do this without overthinking, you've actually learned it.

---

That's all. Hope this saves you some time. Star it if it helped 🙂
