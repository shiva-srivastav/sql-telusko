# MySQL Installation Guide for Windows

This guide provides step-by-step instructions for installing **MySQL** on a Windows system, configuring it, and setting up the necessary environment variables.


### Step 1: Download MySQL Installer
1. Go to the official **MySQL** website: [MySQL.com](https://www.mysql.com/).
2. Navigate to **Downloads** → **MySQL Community (GPL) Downloads**.
3. Click on **MySQL Installer for Windows**.
4. Select the **latest version** available.
5. Choose **Operating System** → **Microsoft Windows**.
6. Click **Download** and wait for the process to complete.


### Step 2: Install MySQL on Windows
1. Locate the **downloaded MySQL Installer** and double-click to run it.
2. Choose a **Setup Type**: Select **Custom**.
3. Select **Products**:
   - Add the following products for installation:
     - **MySQL Server**
     - **MySQL Workbench**
     - **MySQL Shell**
4. Click **NEXT** → **NEXT** → **NEXT**.
5. Set a **MySQL Password** for the root user and note it down.
6. In **Server File Permission**, choose Yes, grant full access.
7. Click **NEXT** → **EXECUTE** → Wait for the installation to complete.
8. Click **FINISH** → **FINISH** to exit the installer.


## Step 3: Configure Environment Variables for MySQL
To use MySQL from the command line, set up the **environment path variable**:

1. Locate the **MySQL installation directory**:
   - Go to the installed location: `MySQL Server -> Bin`
   - **Copy the full path** (e.g., `C:\Program Files\MySQL\MySQL Server X.X\bin`)
2. Open **Environment Variables**:
   - Navigate to **Advanced** → **Environment Variables**.
   - Under **User Variables**, find Path → Click Edit.
   - Click **New** → Paste the copied MySQL **Bin** path.
   - Click **OK** → **OK** to save changes.


## Step 4: Verify MySQL Installation
To confirm MySQL is installed and accessible from the command line:

1. Open **Command Prompt (cmd)**
2. Run the following command:
   ```sh
   mysql --version
   ```
   ✅ If MySQL is installed correctly, you should see an output similar to:
   ```plaintext
   mysql  Ver 8.0.XX for Win64 on x86_64 (MySQL Community Server - GPL)
   ```
