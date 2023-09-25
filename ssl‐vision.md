
![Fotbollsplan](https://github.com/LiU-ToeBiters/wiki/assets/75081269/752dda1f-a86a-4f9e-9a0f-727ea13fcfa9)
Things related to ssl-vision running in the lab.

# Guides

## Access the cameras
The cameras are only accessible from [fetdatorn](fetdatorn). They're of the model **AXIS M3005 Network Camera**. There are four cameras but only two are configured. To access stream on Linux: `ffplay –fflags nobuffer –flags low_delay rtsp://root:root@192.168.1.1/axis-media/media.amp`. 

### Camera 1 (closest to corridor)
- Username/password: [here](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/Cameras%20details.docx?d=w874584b250544826a239818754af4219&csf=1&web=1&e=696OaL)
- Network: The switch at fetdatorn
- IP: 192.168.1.1/24

### Camera 3 (closest to computers)
- Username/password: [here](https://liuonline.sharepoint.com/:w:/r/sites/ToeBiters/Shared%20Documents/Private%20documentation/Cameras%20details.docx?d=w874584b250544826a239818754af4219&csf=1&web=1&e=696OaL)
- Network: The switch at fetdatorn
- IP: 192.168.1.3/24

[Football field setup.pdf](https://github.com/LiU-ToeBiters/wiki/files/12712960/Football.field.setup.pdf)
