`Fetdatorn` is the name of the computer we use to run most shared software solutions. On this page you'll find everything related to it.

# Guides

## X11 Forwarding on Windows
Running GUI applications on Fetdatorn remotely 

Please update this guide with the necessary steps if you encounter any problems 

### Installing a XServer

To run GUI applications on fetdatorn remotely on your own computer a XServer needs to be set up. 

Multiple such xserver applications exist, but simplest is installing GWSL. This can be done by either: 

* A Downloading the GWSL.zip file from here [GWSL.zip](https://liuonline.sharepoint.com/:u:/r/sites/ToeBiters/Shared%20Documents/GWSL/GWSL.zip?csf=1&web=1&e=22Qd7x) and running the executable GWSL (Version 1.4.0). 
* B Building the latest version from source from https://github.com/Opticos/GWSL-Source 
- Download the latest release .zip file. 
- Extract all the files to a suitable location. 
- Open Git Bash (or similar terminal, this guide is based on running the commands in Git Bash). 
- Create a python venv in the extracted directory: python -m venv gwsl_installation 
- Source the venv: source gwsl_installation/Scripts/activate 
- Install all the required packages according to the list on the GitHub. IMPORTANT: Install the lastest version of pyinstaller (remove “==3.5”) 
- Run the command: python build.py 
- Start GWSL by running the GWSL.exe file in the dist/GWSL_*version* directory. 
- It will ask for access to the firewall and such, press “Allow” on all of them.