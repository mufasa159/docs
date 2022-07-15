### Create bootable USB drive on MacOS

1. Connect USB drive to machine
2. Download ISO file  
3. Open terminal  
4. Format USB using following command:
```
diskutil list
diskutil eraseDisk MS-DOS <name> GPT <disk>
```
Example: `diskutil eraseDisk MS-DOS "WIN08" GPT disk3`  

5. Mount the ISO file by running the following:
```
hdutil mount <filepath>
```
Example: `hdutil mount ~/Downloads/Win8.1_x64.iso`

6. Once mounted the new volume will be displayed in terminal
7. Copy the content of mounted ISO volume to formatted USB drive by running the following:
```
cp -rp <mounted_volume_path>/* <formatted_usb_path>
```
Example: `cp -rp /Volumes/IR5_CCSA_X64FRE/* /Volumes/WIN08`

8. Once files are copied successfully, unmount the ISO volume by running:
```
hdiutil unmount <mounted_volume_path>
```
Example: `hdiutil unmount /Volumes/IR5_CCSA_X64FRE`  

9. Eject the USB drive from machine
10. Ready for boot