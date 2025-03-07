# Installation Guide for CellProfiler and Plugins
This guide walks you through installing CellProfiler and its plugins. Adjust the instructions as needed for your operating system (Mac, Windows, and Ubuntu).

## Step 1: Set Up a Conda Environment (Optional but Recommended)
Creating a Conda (<a href='https://docs.anaconda.com/miniconda/install/'>Miniconda installation</a>) environment ensures an isolated setup for CellProfiler, avoiding potential conflicts with other software. Use the following commands:

```
conda create -n cellprofiler python=3.9
conda activate cellprofiler
```

If you prefer not to use a Conda environment, proceed to Step 2: Verify Python Version.

## Step 2: Verify Python Version (For Non-Conda Users)
If you are not creating a Conda environment, verify that the Python version on your system is 3.8 or higher. This guide has been tested with Python 3.8 and 3.9.

- <b>Windows</b>: Ensure Python is added to the system's PATH during installation. If not, add Python to PATH.
- Check if Python is already installed:

Open CMD/Terminal and run:

```
python --version
```
or
```
python3 --version
```

<b>Ubuntu/Mac: </b>

If Python is detected as python3, create an alias to make it accessible as python:

```
alias python=python3
```

## Step 3: Install Dependencies
- Windows:
  -  Microsoft Visual C++ Redistributable: Download and install from <a href='https://aka.ms/vs/17/release/vc_redist.x64.exe'> Microsoft's official website</a>.
  -  Microsoft Visual Studio C++ Build Tools: Download from <a href='https://aka.ms/vs/17/release/vs_BuildTools.exe'>Microsoft's official website</a>. During installation, select <b>Desktop development with C++</b>.
  -  Java JDK 11: Download Java JDK 11 from <a href='https://adoptium.net/temurin/archive/?version=11'>Oracle's website</a>. During installation, check the box labeled Set <b>JAVA_HOME variable </b>.
    Verify installation:
```
java -version
```

-  Ubuntu:
   -  Build Essentials: Install essential development tools, including GCC.
   -  Java JDK 11
```
sudo apt update
sudo apt install build-essential
sudo apt install openjdk-11-jdk
java -version
```

-  Mac:
   -  Xcode Command Line Tools: Install essential development tools, including GCC.
   -  Java JDK 11
```
xcode-select --install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install openjdk@11
java -version
```

## Step 4: Find and Configure JAVA_HOME and JDK_HOME
To ensure proper Java configuration, locate the <b>JAVA_HOME</b> directory (defined during Java installation) and define a new variable, <b>JDK_HOME</b>, with the same value.

- Windows
1. Check if `JAVA_HOME` is Defined: </br>Open Command Prompt and run:
```
echo %JAVA_HOME%
```
If this command outputs a valid directory path (e.g., C:\Program Files\Eclipse Adoptium\jdk-11.0.x), proceed to the next step. If not, manually locate the Java installation directory:</br>
Navigate to the folder where Java was installed (default: C:\Program Files\Eclipse Adoptium or similar).


2. Define the JDK_HOME Variable:
```
Right-click This PC > Properties > Advanced System Settings > Environment Variables.
Under System Variables, click New and create the variable:
Variable Name: JDK_HOME
Variable Value: Full path to the JDK directory (e.g., C:\Program Files\Eclipse Adoptium\jdk-11.0.21.9-hotspot).
```
3. Add JRE Path to the System PATH. </br>
<b>Note:</b> Ensure no conflicting Java paths (e.g., older Java versions, MinGW, or Cygwin64) exist in the PATH.

- Ubuntu
1. Locate the `JAVA_HOME` Path:
</br>
Run the following command to list all Java installations:

```
sudo update-alternatives --config java
```

Note the path to the selected JDK directory (e.g., /usr/lib/jvm/java-11-openjdk-amd64).


2. Define the `JDK_HOME` Variable: </br>
Open your shell configuration file (e.g., `~/.bashrc`) and add the following lines:

```
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export JDK_HOME=$JAVA_HOME
export PATH=$PATH:$JAVA_HOME/bin
```

Save the file and reload the shell configuration:

```
source ~/.bashrc
```

3. Verify the Variables:

Confirm that both JAVA_HOME and JDK_HOME are set correctly:
```
echo $JAVA_HOME
echo $JDK_HOME
```

- Mac
1. Locate the `JAVA_HOME` path:
```
/usr/libexec/java_home -v 11
```
This outputs the JDK path (e.g., /Library/Java/JavaVirtualMachines/jdk-11.0.x.jdk/Contents/Home).

2. Define `JAVA_HOME` and `JDK_HOME`: 

Add the following lines to `~/.zshrc` or `~/.bashrc`:

```
export JAVA_HOME=$(/usr/libexec/java_home -v 11)
export JDK_HOME=$JAVA_HOME
export PATH=$JAVA_HOME/bin:$PATH
```

3. Reload the shell configuration:
```
source ~/.zshrc  # or source ~/.bashrc
```

4. Verify:

```
echo $JAVA_HOME
echo $JDK_HOME
```

## Step 5: Install Required Python Packages
Install Java Bridge:

```
pip install python-javabridge
```

Install MySQL Client:

```
pip install mysqlclient
```

If errors occur, download the `.whl` file from <a href='https://pypi.org/project/mysqlclient/#files'>PyPI</a> and install it manually:

```
pip install mysqlclient-XXX.whl
```


## Step 6: Install CellProfiler and Plugins
- Install CellProfiler:
Download the source code from <a href='https://github.com/CellProfiler/CellProfiler'>GitHub Releases</a>.
Extract the files, navigate to the folder in the terminal, and install:

```
pip install -e .
```

- Install Plugins:
Clone the plugin repository:
```
git clone https://github.com/CellProfiler/CellProfiler-plugins.git
```

Navigate to the plugin folder and install:
```
pip install -e .
```

## Step 7: Additional Package Installation
Install the following packages:
```
pip install cellpose
pip install omnipose
pip install stardist
```

## Step 8: Configure CellProfiler Plugins
Open CellProfiler:
```
cellprofiler
```

Set Plugin Directory: Navigate to `File > Preferences`.</br>
In the CellProfiler plugins directory field, enter the path to the `active_plugins` folder in the plugins directory.
Save and restart CellProfiler.
