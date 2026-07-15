# Installing and Configuring Python on Windows

## Purpose
This guide provides step-by-step instructions for downloading, installing, and verifying Python on a Windows environment.

## Prerequisites
* Operating System: Windows 11 (or Windows 10)
* An active internet connection
* Administrative privileges on the host machine

## Installation Procedure

### Step 1: Download the Python Installer
1. Open a web browser and navigate to the official Python downloads page: `https://www.python.org/downloads/`.
2. Click the **Download Python** button to download the latest stable installer executable for Windows.

### Step 2: Run the Installer
1. Locate the downloaded `.exe` file in your file explorer and double-click to run it.
2. In the installation wizard window, check the box labeled **Add Python.exe to PATH**. 
   * *Note: Enabling this option ensures you can execute Python commands globally from any terminal interface.*
3. Select **Install Now** to proceed with the standard installation configurations.
4. Once completed, click **Close** to exit the setup wizard.

## Verification
To verify that Python was successfully installed and added to your environment variables:

1. Open the **Command Prompt** or **PowerShell**.
2. Execute the following command:
   ```bash
   python --version