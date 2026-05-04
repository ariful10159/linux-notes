

# 🚀 Flutter Environment Setup on Linux

This guide covers the complete step-by-step process to set up the Flutter SDK environment on a Linux system, configure the path variables, and fix common ownership permissions.

---

### Prerequisites
Make sure you have downloaded the Flutter SDK and placed it in your desired directory (for this guide, the path is assumed to be `/mnt/extra/flutter/bin/`).

---

### Step 1: Check your Shell
Before setting the environment path, you need to know which shell you are using (Bash or Zsh). Open your terminal and run:

```bash
echo $SHELL
```

* **Possible Outputs:** * `/usr/bin/zsh` (Zsh)
  * `/bin/bash` (Bash)

---

### Step 2: Configure Environment Variables

Open your terminal and edit the configuration file corresponding to your shell.

#### A. If you are using Zsh:
1. Open the file with the `nano` text editor:
   ```bash
   nano ~/.zshrc
   ```
2. Scroll down to the very bottom and add the following line:
   ```bash
   export PATH="$PATH:/mnt/extra/flutter/bin"
   ```
3. Save the file by pressing **Ctrl + O**, then press **Enter**. Exit the editor by pressing **Ctrl + X**.

#### B. If you are using Bash:
1. Open the file with the `nano` text editor:
   ```bash
   nano ~/.bashrc
   ```
2. Scroll down to the very bottom and add the following line:
   ```bash
   export PATH="$PATH:/mnt/extra/flutter/bin"
   ```
3. Save the file by pressing **Ctrl + O**, then press **Enter**. Exit the editor by pressing **Ctrl + X**.

---

### Step 3: Apply the Changes

Reload your shell configurations so the new path takes effect immediately:

* **For Zsh:**
  ```bash
  source ~/.zshrc
  ```
* **For Bash:**
  ```bash
  source ~/.bashrc
  ```

---

### Step 4: Fix Git Dubious Ownership (If Required)

If you store the Flutter SDK on an external or separate drive, Git might throw a "dubious ownership" error. Fix it by marking the directory as safe:

```bash
git config --global --add safe.directory /mnt/extra/flutter
```

---

### Step 5: Verify the Installation

To verify that the Flutter CLI is successfully installed and recognized by your system, run:

```bash
flutter --version
```
### 📌 View PATH in Linux (Line by Line)

To display each directory in the `PATH` environment variable on a separate line:

```bash
echo $PATH | tr ':' '\n'
```

✅ This splits the `PATH` using `:` and prints each entry line by line, making it easier to read and understand.

