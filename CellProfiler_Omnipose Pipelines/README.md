# Installation Guide for CellProfiler and Plugins
This guide walks you through installing CellProfiler and its plugins. Adjust the instructions as needed for your operating system (Windows or Ubuntu).

## Step 1: Set Up a Conda Environment (Optional but Recommended)
Creating a Conda environment ensures an isolated setup for CellProfiler, avoiding potential conflicts with other software. Use the following commands:

```
conda create -n cellprofiler python=3.9
conda activate cellprofiler
```

If you prefer not to use a Conda environment, proceed to Step 2: Verify Python Version.

## Step 2: Verify Python Version (For Non-Conda Users)
If you are not creating a Conda environment, verify that the Python version on your system is 3.8 or higher. This guide has been tested with Python 3.8 and 3.9.

- <b>Windows</b>: Ensure Python is added to the system's PATH during installation. If not, add Python to PATH.
- <b>Ubuntu</b>: Check if Python is already installed:
```
python --version
```
or
```
python3 --version
```
If Python is detected as python3, create an alias to make it accessible as python:

```
alias python=python3
```

## Step 3: Install Dependencies
- Windows:
  -  Microsoft Visual C++ Redistributable: Download and install from Microsoft's official website.
  -  Microsoft Visual Studio C++ Build Tools: Download from Visual Studio website. During installation, select <b>Desktop development with C++</b>.
  -  Java JDK 11: Download Java JDK 11 from Oracle's website. During installation, check the box labeled Set <b>JAVA_HOME variable </b>.
    Verify installation:
```
java -version
```

-  Ubuntu:
  -  Build Essentials: Install essential development tools, including GCC:
```
sudo apt update
sudo apt install build-essential
```
  -  Java JDK 11: Install Java using the following commands:
```
sudo apt update
sudo apt install openjdk-11-jdk
java -version
```
