---
name: SETUP_GUIDE
description: Click-by-click setup of the brain vault: local folder, Obsidian, private GitHub repository, and keeping all three in sync.
status: active
last_reviewed: 2026-10-15
---

# Setup guide: local folder, Obsidian, GitHub

This guide assumes a **Windows** computer. If you are on a Mac, tell Claude and it will give you the Mac version.

**Time needed:** about 30 to 45 minutes the first time.

## The big picture (read this once)

- Your **folder** on your computer is the real thing. It is the master copy.
- **Obsidian** is just a comfortable window onto that folder. It does not store anything itself.
- **GitHub** holds a backup copy online. Other AIs can read it from there.
- The rule: **you only ever change things in the folder (through Obsidian). GitHub just receives copies.** Never edit files on the GitHub website.

---

## PART A: Put the folder on your computer

1. Find the file **John-Brain.zip** that Claude sent you and download it.
2. Open **File Explorer** (the yellow folder icon on the taskbar).
3. Click **Documents** on the left side.
4. Find **John-Brain.zip** (usually in **Downloads**). Drag it into **Documents**, or cut and paste it there.
5. Right-click **John-Brain.zip**. Click **Extract All...** Click **Extract**.
6. You now have a folder called **John-Brain** inside Documents. Open it. You should see folders named 00, 01, 02 and so on, plus a file called **00_READ_FIRST.md**.

If you see another **John-Brain** folder inside the first one, that is normal for zips. Drag the **inner** one out into Documents and delete the empty outer one, so the path is exactly `Documents\John-Brain`.

---

## PART B: Install Obsidian and open the folder

1. Open your web browser. Go to **obsidian.md**.
2. Click **Download**. Choose the **Windows** installer. Run it when it finishes downloading. Click through the installer with the default choices.
3. Open **Obsidian**.
4. Click **Open folder as vault**.
5. Click **Open**, then choose **Documents\John-Brain**. Click **Select Folder**.
6. If it asks "Trust author and enable plugins?", click **Trust author and enable plugins**. It is your own folder.
7. On the left you will see your folders. Click **00_READ_FIRST** to read it. If the text looks like plain code with symbols, click the small **book icon** at the top right to switch to reading view.

**Two settings to change now:**

8. Click the **gear icon** at the bottom left (Settings).
9. Click **Files and links** in the left list.
10. Turn **ON** "Automatically update internal links". This keeps links working when you rename a note.
11. Click the box next to **Default location for new notes**. Choose **In the folder specified below**. In the box that appears, type `05_Inbox_To_Review`. New notes will land there so nothing gets lost.
12. Close Settings (click the X, or press **Esc**).

---

## PART C: Create the private GitHub repository

A "repository" is just a folder on GitHub.

1. In your browser, go to **github.com** and sign in to the account you already use for LEGAiSEE.
2. Click the **plus (+)** at the top right. Click **New repository**.
3. In **Repository name**, type: `john-brain`
4. Under visibility, click **Private**. **This is important. Do not choose Public.**
5. **Leave every checkbox empty.** Do NOT tick "Add a README file", ".gitignore", or "license". The folder you have already contains what it needs.
6. Click **Create repository**.
7. You will land on a page with a web address like `https://github.com/carrmultimedia-arch/john-brain`. Keep this page open. If your username is different from `carrmultimedia-arch`, use the one you see in the address.

---

## PART D: Make sure Git is installed on your computer

Git is the small program that does the copying to GitHub.

1. Press the **Windows key** on your keyboard. Type `cmd`. Press **Enter**. A black window opens. This is the "terminal".
2. Paste this and press **Enter**:

**PASTE 1 of 1 (check for Git)**
```
git --version
```

3. If it shows something like `git version 2.4x`, **skip to Part E**.
4. If it says "not recognized", go to **git-scm.com**, click **Download for Windows**, run the installer, and click **Next** through every screen without changing anything. Then close the black window, open a new one (step 1 above), and run the command again to confirm.

---

## PART E: First upload (done once, in the terminal)

Do these **one at a time**. Paste one box, press **Enter**, wait for it to finish, then paste the next. Each box is separate.

In the black window:

**PASTE 1 of 8 (go into your folder)**
```
cd %USERPROFILE%\Documents\John-Brain
```

**PASTE 2 of 8 (turn the folder into a Git folder)**
```
git init -b main
```

**PASTE 3 of 8 (tell Git your name)**
```
git config user.name "John Carr"
```

**PASTE 4 of 8 (tell Git your email: use the email on your GitHub account; replace the part in capitals)**
```
git config user.email "YOUR-GITHUB-EMAIL-HERE"
```

**PASTE 5 of 8 (gather all the files)**
```
git add .
```

**PASTE 6 of 8 (save the first snapshot)**
```
git commit -m "First commit: starting the brain vault"
```

**PASTE 7 of 8 (point at your GitHub repository. Check the address matches the page you kept open)**
```
git remote add origin https://github.com/carrmultimedia-arch/john-brain.git
```

**PASTE 8 of 8 (send it up)**
```
git push -u origin main
```

**What happens at the last step:** a window pops up asking you to sign in to GitHub. Click **Sign in with your browser**. Your browser opens. Click **Authorize**. Then go back to the black window. It should say something like "branch 'main' set up to track 'origin/main'".

**If instead it asks for a "Password":** GitHub no longer accepts your normal password here. You need a one-time code called a token:
1. On github.com click your **picture** at the top right, then **Settings**.
2. Scroll to the bottom of the left list. Click **Developer settings**.
3. Click **Personal access tokens**, then **Fine-grained tokens**, then **Generate new token**.
4. Name it `john-brain`. Set **Expiration** to 1 year.
5. Under **Repository access** click **Only select repositories**, then choose **john-brain**.
6. Click **Repository permissions**, find **Contents**, and change it to **Read and write**.
7. Click **Generate token**. **Copy the token now.** GitHub only shows it once.
8. Paste the token into the black window where it asked for a password, press **Enter**. Save the token somewhere safe that is **not** inside the John-Brain folder (a password manager, or a note kept elsewhere).

**Check it worked:** go to your repository page on github.com and press **F5** to refresh. You should now see your folders and files.

---

## PART F: Add the Obsidian Git plugin (so Obsidian does the copying for you)

1. In Obsidian, click the **gear icon** (bottom left).
2. Click **Community plugins** in the left list.
3. If you see "Restricted mode is on", click **Turn on community plugins**. Click **Turn on** to confirm.
4. Click **Browse**.
5. In the search box type: `Obsidian Git`
6. Click the one named **Obsidian Git** (by Vinzent). Click **Install**. When it finishes, click **Enable**.
7. Close the plugin window. Back in Settings, scroll down the left list to the **Community plugins** section and click **Git** (or **Obsidian Git**).
8. Set these:
   - **Auto commit-and-sync interval (minutes):** type `30`. (This copies your work to GitHub every 30 minutes. Type 0 if you'd rather do it by hand only.)
   - **Pull on startup:** turn **ON**. (This brings in any changes each time you open Obsidian.)
   - **Auto pull interval:** leave at 0.
9. Close Settings.

**Test it:**
1. In Obsidian, press **Ctrl + N** to make a new note. Type a title like `test` and a sentence. It lands in `05_Inbox_To_Review`.
2. Press **Ctrl + P** (opens the command list). Type `commit-and-sync`. Click **Obsidian Git: Commit-and-sync**.
3. Wait for a small "Pushed" message at the bottom.
4. In your browser, refresh the GitHub page and open `05_Inbox_To_Review`. Your test note should be there.
5. Delete the test note in Obsidian (right-click it in the left list, **Delete**), and run **Commit-and-sync** again.

You are done. The three parts are now connected.

---

## PART G: Let an AI read it

You have three ways. Start with the first.

1. **Simplest, works with every AI:** at the start of a chat, attach or paste **00_READ_FIRST.md**, **01_About_John/profile.md** and **02_Governance/how-to-work-with-john.md**. Then add the one project note you are working on.
2. **Connect the GitHub repository:** Claude, ChatGPT and others have a setting to connect a GitHub repository to a project. Menu names change often. Ask the AI "how do I connect a GitHub repo to a project?" and it will give current steps. Pick `john-brain`.
3. **Link only:** because the repo is private, an AI cannot open a plain link to it. Do not make it public.

---

## Troubleshooting

| What you see | What to do |
|---|---|
| "git is not recognized" | Part D, step 4. Install Git, then open a **new** black window. |
| "remote origin already exists" | You ran Paste 7 twice. Ignore it and go on to Paste 8. |
| "rejected" or "non-fast-forward" | Something was added on the GitHub website. Run `git pull --rebase origin main` and then try Paste 8 again. Better: never edit on the website. |
| Obsidian Git says "No Git repository" | Part E was not completed in the right folder. Redo Paste 1 and confirm the folder name. |
| Obsidian Git shows red errors after you changed files in two places | Stop. Do not click anything else. Copy the message and ask Claude. |
| Push asks for a password | See the token steps in Part E. |
