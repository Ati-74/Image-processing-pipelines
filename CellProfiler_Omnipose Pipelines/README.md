

1. Verify and Install Python</br>
   a. Check Your Python Version

     Open a terminal:
     - On Windows: Launch the Command Prompt (CMD) by pressing `Win + R`, typing `cmd`, and pressing Enter.
     - On Ubuntu: Open a terminal by pressing `Ctrl + Alt + T`.
     Run the following command to check the installed Python version:
```
python --version
```
(On some systems, use `python3 --version`.)

   b. Ensure Compatibility
   
CellProfiler-Omnipose is compatible only with Python 3.8 and Python 3.9.

If your Python version is below 3.8, above 3.9, or not installed, proceed with the installation steps below.

   c. Install Python
      - For Windows:
      Download the required version from the official Python website:
      Download <a href="https://www.python.org/downloads/release/python-380/">Python 3.8</a></br>
      Download <a href="https://www.python.org/downloads/release/python-390/">Python 3.9</a>
Run the installer and select Windows x86-64 executable installer.
During the installation, ensure you check the box for Add Python to PATH (<b>add to PATH</b>) before clicking Install.
      - For Ubuntu:

Update your package list:
```
sudo apt update
```
Install the desired Python version:
For Python 3.8:
```
sudo apt install python3.8
```
For Python 3.9:
```
sudo apt install python3.9
```
