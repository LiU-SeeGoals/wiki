**Fetdatorn** is the name of the computer we use to run most shared software solutions. On this page you'll find everything related to it.

# Guides

## Accessing from the inside
As long as you're on campus you should be able to connect to Fetdatorn without problem, see [this](https://docs.google.com/document/d/1-iWG2_kSW-0iN2fS-5-W1LanjvWFRzeXaEJyUMzvuME/edit).

## Accessing from the outside
Since the university offers a way to access their network through a VPN it's also possible to access Fetdatorn remotely. You'll need two things for this:

1. [Two-factor authentication enabled](https://tsv.liu.se/) on your school account, 
2. and be connected to the [student VPN](https://liudesk.liu.se/tas/public/ssp/content/detail/knowledgeitem?unid=5781469d338240abb741d51b97eccb8a). 

You can then SSH to Fetdatorn using `ssh.edu.liu.se` as the jump host, see [this](https://docs.google.com/document/d/1-iWG2_kSW-0iN2fS-5-W1LanjvWFRzeXaEJyUMzvuME/edit). This is guaranteed to always work. If, for some reason, you can't access the LiU VPN then check [this](https://docs.google.com/document/d/1MFJEkQNlpNgPn907wmUEY2m6iiJhb6ONw5ayRHKsJSY/edit).

## Connecting to it with ThinLinc
To access Fetdatorn with ThinLinc you'll have to do it like [this](https://docs.google.com/document/d/1MFJEkQNlpNgPn907wmUEY2m6iiJhb6ONw5ayRHKsJSY/edit). Basically you set it up and connect to Fetdatorn's IP and it should work. For details about thinlinc, check [this](https://docs.google.com/document/d/1vqRh1PUEqXrd5Wixka6bvFZFpDgbWbjeE50rzuy8tFk/edit).

**OBS!** If you have an active ThinLinc session you won't be able to login to Fetdatorn physically, first logout from ThinLinc.

## X11 Forwarding on Windows
This is for running GUI applications on Fetdatorn remotely. Please update this guide with the necessary steps if you encounter any problems 

### Installing a XServer
To run GUI applications on Fetdatorn remotely on your own computer a XServer needs to be set up.  Multiple such XServer applications exist, but simplest is installing GWSL. This can be done by either: 

* A) Downloading the GWSL.zip file from here [GWSL.zip](https://drive.google.com/file/d/1el9KVTE4EcIjH6JBlKWOkCBekzAt7_tg/view?usp=drive_link) and running the executable GWSL (Version 1.4.0). 
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
  1. Create (or update) your `.ssh/config` file (the standard directory location) according to one of [these](https://docs.google.com/document/d/1-iWG2_kSW-0iN2fS-5-W1LanjvWFRzeXaEJyUMzvuME/edit) (see more instructions above how to actually access the computer from inside/outside).
  2.  Open a Git Bash terminal and set the DISPLAY environment variable to the one used by GWSL. To check this do the following: 
        * a. Press the little upwards pointing arrow in the bottom right corner of your screen  
             ![ssh_to_fetdatorn_img1](https://github.com/LiU-ToeBiters/wiki/assets/86022094/8be7c9cc-1ac2-4cb3-aaa3-e7736edff941)
        * b. Click the icon with the two orange/yellow boxes.  
             ![ssh_to_fetdatorn_img2](https://github.com/LiU-ToeBiters/wiki/assets/86022094/5a1e018c-2d81-4c27-9765-3bdb7e0e804f)
        * c. At the top it says what DISPLAY the XServer is running on, in this case it is “localhost:0.0” 
  3. Run the command: `export DISPLAY=localhost:0.0`
  4. Now SSH to fetdatorn, run the command: `ssh <Host>` (depending on which config you chose).
  5. You’re in! 
  6. Try running xeyes in the terminal. If everything works you should have a pair of eyes on your local machine following your mouse cursor.