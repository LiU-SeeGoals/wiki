**Fetdatorn** is the name of the computer we use to run most shared software solutions. On this page you'll find everything related to it.

# Guides

## Accessing from the inside
As long as you're on campus you should be able to connect to Fetdatorn without problem, see [this](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/fetdatorn_ssh_configs.docx?d=wb407296122ee44b0a4e7c8fbd6ac7bbb&csf=1&web=1&e=hcYoez).

## Accessing from the outside
Since the university offers a way to access their network through a VPN it's also possible to access Fetdatorn remotely. You'll need two things for this:

1. [Two-factor authentication enabled](https://tsv.liu.se/) on your school account, 
2. and be connected to the [student VPN](https://liudesk.liu.se/tas/public/ssp/content/detail/knowledgeitem?unid=5781469d338240abb741d51b97eccb8a). 

You can then SSH to Fetdatorn using ssh.edu.liu.se as the jump host, see [this](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/fetdatorn_ssh_configs.docx?d=wb407296122ee44b0a4e7c8fbd6ac7bbb&csf=1&web=1&e=hcYoez). This is guaranteed to always work. If, for some reason, you can't access the LiU VPN then check [this](https://liuonline.sharepoint.com/sites/ToeBiters/_layouts/15/doc.aspx?sourcedoc=%7B3fb2ffb7-42aa-4734-bf3a-f748f3d8f4c2%7D&action=edit).

## X11 Forwarding on Windows
This is for running GUI applications on Fetdatorn remotely. Please update this guide with the necessary steps if you encounter any problems 

### Installing a XServer
To run GUI applications on Fetdatorn remotely on your own computer a XServer needs to be set up.  Multiple such XServer applications exist, but simplest is installing GWSL. This can be done by either: 

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

### SSH to Fetdatorn 
  1. Create (or update) your `.ssh/config` file (the standard directory location) according to one of [these](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/fetdatorn_ssh_configs.docx?d=wb407296122ee44b0a4e7c8fbd6ac7bbb&csf=1&web=1&e=hcYoez).
  2.  Open a Git Bash terminal and set the DISPLAY environment variable to the one used by GWSL. To check this do the following: 
        * a. Press the little upwards pointing arrow in the bottom right corner of your screen  
             ![ssh_to_fetdatorn_img1](https://github.com/LiU-ToeBiters/wiki/assets/86022094/8be7c9cc-1ac2-4cb3-aaa3-e7736edff941)
        * b. Click the icon with the two orange/yellow boxes.  
             ![ssh_to_fetdatorn_img2](https://github.com/LiU-ToeBiters/wiki/assets/86022094/5a1e018c-2d81-4c27-9765-3bdb7e0e804f)
        * c. At the top it says what DISPLAY the XServer is running on, in this case it is “localhost:0.0” 
  3. Run the command: `export DISPLAY=localhost:0.0`
  4. Now SSH to fetdatorn, run the command: `ssh fetdatorn`
  5. Enter the password to the fia proxy-jump and then the password to your user on fetdatorn. 
  6. You’re in! 
  7. Try running xeyes in the terminal. If everything works you should have a pair of eyes on your local machine following your mouse cursor.