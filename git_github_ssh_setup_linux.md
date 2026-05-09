# Git & GitHub SSH Setup on Ubuntu Linux

A complete beginner-friendly guide to setting up Git and GitHub SSH authentication on Ubuntu Linux.

---

# 1. Check Git Installation

Open Terminal and run:

```bash
git --version
```

Example output:

```bash
git version 2.53.0
```

If Git is not installed:

```bash
sudo apt update
sudo apt install git
```

---

# 2. Configure Git Username and Email

Set your GitHub username:

```bash
git config --global user.name "YOUR_GITHUB_USERNAME"
```

Set your GitHub email:

```bash
git config --global user.email "YOUR_GITHUB_EMAIL"
```

Example:

```bash
git config --global user.name "ariful10159"
git config --global user.email "arifulislammasum97@gmail.com"
```

Check configuration:

```bash
git config --list
```

---

# 3. Generate SSH Key

Create a new SSH key:

```bash
ssh-keygen -t ed25519 -C "YOUR_GITHUB_EMAIL"
```

Example:

```bash
ssh-keygen -t ed25519 -C "arifulislammasum97@gmail.com"
```

---

## During Setup

### Save location

You will see:

```bash
Enter file in which to save the key
```

Press:

```bash
Enter
```

### Passphrase

You will see:

```bash
Enter passphrase
```

You can:

* Press `Enter` for no passphrase
* Or set a password for extra security

---

# 4. Start SSH Agent

Run:

```bash
eval "$(ssh-agent -s)"
```

---

# 5. Add SSH Key to SSH Agent

Run:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

# 6. Copy Public SSH Key

Show the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Example output:

```bash
ssh-ed25519 ..........................hw1IRKb1BRwW2la6cgFcthjwfWVqVMQJIJcK6 arifulislammasum97@gmail.com
```

Copy the entire output.

---

# 7. Add SSH Key to GitHub

Open GitHub SSH settings:

[GitHub SSH Keys Settings](https://github.com/settings/keys?utm_source=chatgpt.com)

Then:

1. Click **New SSH key**
2. Title:

```text
Ubuntu Victus
```

3. Paste the copied SSH key
4. Click **Add SSH key**

---

# 8. Test GitHub SSH Connection

Run:

```bash
ssh -T git@github.com
```

First time you may see:

```bash
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type:

```bash
yes
```

Successful output:

```bash
Hi YOUR_USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
```

Example:

```bash
Hi ariful10159! You've successfully authenticated, but GitHub does not provide shell access.
```

---

# 9. Clone Repository Using SSH

Clone your repository:

```bash
git clone git@github.com:USERNAME/REPOSITORY_NAME.git
```

Example:

```bash
git clone git@github.com:ariful10159/Blood_Donation_Application.git
```

---

# 10. Useful Git Commands

## Check repository status

```bash
git status
```

## Add all files

```bash
git add .
```

## Commit changes

```bash
git commit -m "Initial commit"
```

## Push to GitHub

```bash
git push
```

## Pull latest changes

```bash
git pull
```

---

# 11. Recommended Project Location on Linux

Instead of using external mounted drives like:

```text
/mnt/extra/
```

Use:

```bash
~/Projects
```

Create Projects folder:

```bash
mkdir -p ~/Projects
```

Move into folder:

```bash
cd ~/Projects
```

Clone repositories there for better stability and performance.

---

# 12. Common Problems and Solutions

## Problem: Password authentication failed

Error:

```bash
Password authentication is not supported for Git operations.
```

Solution:

* Use SSH authentication instead of GitHub password.

---

## Problem: SSH connection confirmation appears every time

Remove old known hosts:

```bash
rm ~/.ssh/known_hosts
```

Then reconnect:

```bash
ssh -T git@github.com
```

---

# Final Result

After completing all steps:

* Git is installed
* GitHub account connected
* SSH authentication enabled
* No password required for push/pull/clone
* Ubuntu ready for professional Git workflow

---

# Author

Ariful Islam Masum
GitHub: [ariful10159 GitHub Profile](https://github.com/ariful10159?utm_source=chatgpt.com)
