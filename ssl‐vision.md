Things related to ssl-vision running in the lab.

# Guides

## Access the cameras
The cameras are only accessible from [fetdatorn](fetdatorn). They're of the model **AXIS M3005 Network Camera**. There are four cameras but only two are configured. To access stream on Linux: `ffplay –fflags nobuffer –flags low_delay rtsp://root:root@192.168.1.1/axis-media/media.amp`. 

### Camera 1 (closest to corridor)
- Username: root
- Password: root
- Network: The switch at fetdatorn
- IP: 192.168.1.1/24

### Camera 3 (closest to computers)
- Username: root
- Password: root
- Network: The switch at fetdatorn
- IP: 192.168.1.3/24