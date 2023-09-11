# 3.5inch-DPI-LCD-DTBO
DTBO files for 3.5inch DPI LCD by Waveshare
If you don't know the difference between the two branches of Raspberry Pi OS, you can check the following introduction #Introducing the Raspberry Pi OS fork.
For Raspberry Pi OS Bullseye branch

Please download the latest version of the image from the Raspberry Pi official website.

1. Download the compressed file to the PC, and extract the img file.
2. Connect the TF card to the PC and use SDFormatter to format the TF card.
3. Open the Win32DiskImager software, select the system image prepared in step 1, and click write to burn the system image.
4. After the programming is completed, open the config.txt file in the root directory of the TF card, add the following code at the end of config.txt, and save it.

dtoverlay=vc4-kms-v3d
dtoverlay=vc4-kms-DPI-35inch
dtoverlay=waveshare-35dpi-3b-4b
dtoverlay=waveshare-35dpi-3b
dtoverlay=waveshare-35dpi-4b

5. Download the 3.5inch DPI LCD DTBO file and extract the dtbo files. Copy these files to the overlays directory (/boot/overlays/).
6. Insert the TF card into the Raspberry Pi, power on the Raspberry Pi, and wait for more than 30 seconds to display normally.
For Raspberry Pi OS Buster branch and Ubuntu system

1. Open the config.txt file in the root directory of the TF card, add the following code at the end of config.txt, save, and safely eject the TF card.

gpio=0-9=a2
gpio=12-17=a2
gpio=20-25=a2
dtoverlay=dpi18
enable_dpi_lcd=1
display_default_lcd=1
extra_transpose_buffer=2
dpi_group=2
dpi_mode=87
dpi_output_format=0x6f006
hdmi_timings=640 0 20 10 10 480 0 10 5 5 0 0 0 60 0 60000000 1
dtoverlay=waveshare-35dpi-3b-4b
dtoverlay=waveshare-35dpi-3b
dtoverlay=waveshare-35dpi-4b

Note: If it is Raspberry Pi 4, also need to comment out dtoverlay=vc4-fkms-V3D.

2. Download the 3.5inch DPI LCD DTBO file and extract the dtbo files. Copy these files to the overlays directory (/boot/overlays/).
3. Save and quit the TF card safely, and insert the TF card into the Raspberry Pi.
4. Insert the 3.5-inch DPI LCD into the 40PIN GPIO interface of the Raspberry Pi, power on the Raspberry Pi, and wait for about ten seconds to display normally. 
