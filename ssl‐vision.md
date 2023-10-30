Things related to ssl-vision running in the lab.

# Guides

## Access the cameras
The cameras are only accessible from [fetdatorn](fetdatorn). They're of the model **AXIS M3005 Network Camera**. There are four cameras but only two are configured. To access stream on Linux: `ffplay –fflags nobuffer –flags low_delay rtsp://root:root@192.168.1.1/axis-media/media.amp`. It's also possible to access the cameras by typing the ip-address into a browser.

### Camera 1 (closest to corridor)
- Username/password: [here](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/Cameras%20details.docx?d=w874584b250544826a239818754af4219&csf=1&web=1&e=696OaL)
- Network: The switch at fetdatorn
- IP: 192.168.1.1/24

### Camera 3 (closest to computers)
- Username/password: [here](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/Cameras%20details.docx?d=w874584b250544826a239818754af4219&csf=1&web=1&e=696OaL)
- Network: The switch at fetdatorn
- IP: 192.168.1.3/24

### Can't connect?
If you can't connect to the cameras, do the following:
1. Run the command `ip addr`
2. Check if `enp4s0` has the IP `192.168.1.10/24`. 
3. If not, run the command `ip addr add 192.168.1.10/24 dev enp4s0`

## Run SSL-Vision
Before you can run SSL-Vision, it needs to be compiled. Run the following commands:
1. `make configure_vapix`
2. `make`

You can now run the program by typing `./bin/vision`

## Set up camera stream
After opening SSL-Vision, find the tree on the left side of the window. Choose a thread to put the stream on (ex `Thread 0`) and open `Image Capture -> VAPIX -> Capture Settings` and fill in the fields. To start the stream, open `Image Capture -> Capture Control` and press `start capture`.

## Field Line Calibration
To calibrate the field lines, go into the `Camera Calibration` tab in SSL-vision. The `Line Search Corridor Width` specifies the area in which SSL-vision will look for lines.

1. Change the `Camera Height` and `Distortion` parameters by dragging their sliders.
2. Adjust the `Line search Corridor Width` parameter so that all lines are within the boundaries displayed in SSL-vision as blue. 
>If you can't see these lines, go to the tab `Thread x/Visualization` (x is the id of the thread you are using) and make sure the `detected edges` option is set to True.
3. Press the `Detect additional calibration points` button followed by the `Do full calibration` button.
4. If the camera position, represented in SSL-vision by a red cross, is not located at the correct location, start over from step 1. 


# Football Field Setup
> TODO: Make a nicer sketch
<img src="https://github.com/LiU-ToeBiters/wiki/assets/75081269/752dda1f-a86a-4f9e-9a0f-727ea13fcfa9" alt="Football Field Setup" width="600"/>

