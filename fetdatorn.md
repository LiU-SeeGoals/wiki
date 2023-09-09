`Fetdatorn` is the name of the computer we use to run most shared software solutions. On this page you'll find everything related to it.

# Guides

## Accessing from the outside


## X11 Forwarding on Windows
Running GUI applications on Fetdatorn remotely 

Please update this guide with the necessary steps if you encounter any problems 

### Installing a XServer

To run GUI applications on fetdatorn remotely on your own computer a XServer needs to be set up. 

Multiple such xserver applications exist, but simplest is installing GWSL. This can be done by either: 

* A) Downloading the GWSL.zip file from here [GWSL.zip](https://liuonline.sharepoint.com/:u:/r/sites/ToeBiters/Shared%20Documents/Files/GWSL.zip?csf=1&web=1&e=XSHDkE) and running the executable GWSL (Version 1.4.0). 
* B) Building the latest version from source from their [github repo](https://github.com/Opticos/GWSL-Source).
  1. Download the latest release .zip file. 
  2. Extract all the files to a suitable location. 
  3. Open Git Bash (or similar terminal, this guide is based on running the commands in Git Bash). 
  4. Create a python venv in the extracted directory: `python -m venv gwsl_installation `
  5. Source the venv: `source gwsl_installation/Scripts/activate`
  6. Install all the required packages according to the list on the GitHub. IMPORTANT: Install the lastest version of pyinstaller (remove “==3.5”) 
  7. Run the command: `python build.py `
  8. Start GWSL by running the GWSL.exe file in the dist/GWSL_*version* directory. 
  9. It will ask for access to the firewall and such, press “Allow” on all of them.