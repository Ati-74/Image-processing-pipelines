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

