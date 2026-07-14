<h1 align="center">Instructions for Windows</h1>
<hr>

---


## 1. Webots Installation

> [!IMPORTANT] 
> Webots runs on Windows 10 and Windows 8.1 (64-bit versions only).

In order to check whether your system is 64-bit or not, kindly follow these two steps.

1. Open the `file explorer` in your PC/Laptop. Right click on `This PC` and select `Properties` as highlighted (with red box) in the figure below.

<p align="center"><img src="./images/This_PC.png"></p>

2. Then in System, the System type is specified as shown below:

<p align="center"><img src="./images/64-bit_os.png"></p>

- To install Webots <u><a href="https://www.cyberbotics.com/#download" target="_blank">click here</a></u>. This will lead you to the official website of Webots as shown in the image below:

<p align="center">
  <img src="./images/download_1.png" width="600" height="300">
</p>

- Click on `Download`. Select `Windows Installer (.exe)` and then an executable file will automatically get downloaded on your system.

- Double-click the downloaded file `webots-R2025a_setup.exe` to commence the installation and follow the below installation instructions:

1. Click on `Install for all users (recommended)`.

<p align="center">
  <img src="./images/windows_1.png">
</p>

2. Enter the path where you need the software to be installed (or continue with the default path) and click on `Next`.

<p align="center">
  <img src="./images/windows_2.png">
</p>

3. Enter the folder name where you want to create a program's shortcut and click on `Next`.

<p align="center">
  <img src="./images/windows_3.png">
</p>

4. Then you will see a dialog box as shown in the image below. Click on `Install`.

<p align="center">
  <img src="./images/windows_4.png">
</p>

<p align="center">
  <img src="./images/windows_5.png">
</p>

5. Click on `Finish`.

<p align="center">
  <img src="./images/windows_6.png">
</p>

> [!NOTE]
> Install Python for your operating system as explained below. After that follow instructions for setting up environment for Python in Webots.

---

## 2. Python Installation

1. <u><a href="https://www.python.org/ftp/python/3.14.0/python-3.14.0-amd64.exe" download>Click here</a></u> to download Python 3.14.0.
2. On double clicking the `.exe` file (or right click → **Run as administrator**), this window will appear.

<p align="center">
  <img src="./images/1.png" width="500" height="300">
</p>

3. Click on <b>“Add python.exe to PATH”</b> in order to add Python’s installed path to environment variables.

<p align="center">
  <img src="./images/2.png" width="500" height="300">
</p>

4. The installation screen will ask you if you want regular or custom installation. Do not customize and hence do NOT select “Custom Install”.  
   Click on <b>“Install Now”.</b> This will start the installation of Python on your system. You might be asked for administrator permissions to install the same, say “Yes” in that case.

<p align="center">
  <img src="./images/3.png" width="500" height="300">
</p>

This might take some time to complete.

<p align="center">
  <img src="./images/4.png" width="500" height="300">
</p>

5. Click **Yes** if the pop up asks for making changes to the device as shown in the below image:

<p align="center">
  <img src="./images/4.5.png" width="500" height="300">
</p>

6. Click on <b>`Close`.</b>

<p align="center">
  <img src="./images/5.png" width="500" height="300">
</p>

7. Python 3.12.5 is thus successfully installed. To verify software installation, type **“cmd”** in the search box on Windows as shown below to open Command Prompt.

<p align="center">
  <img src="./images/6.png" width="500" height="400">
</p>

8. In Command Prompt, type `python --version` and press Enter. You’ll see `Python 3.14.0` appears in the next line.

<p align="center">
  <img src="./images/7.png" width="500" height="300">
</p>

---

## 3. Setting up environment for Python in Webots

1. For setting up environment for Python in Webots, go to the `Tools` menu and click on `Preferences`.

<p align="center">
  <img src="./images/python_1.png" width="600" height="300">
</p>

2. The command to use Python is usually preset as shown in the image below:

<p align="center">
  <img src="./images/python_2.png" width="500" height="300">
</p>
