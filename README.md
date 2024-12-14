# Add the games from your NAS in Linux

MAKE SURE YOU INSTALL STEAM DIRECTLY, NOT AS AN FLATPAK!

### Open your terminal and enter

````
id -u
````

and 

````
id -g
````

Write these numbers down somewhere

### Now type in

````
sudo su
````

### Enter your password and then type

````
sudo nano /etc/fstab
````

### Add the following at the end of the file (in a new line)

````
//[IP or Hostname of your NAS]/[Path to Steamapps folder]/steamapps /home/[Your Linux User]/.local/share/Steam/steamapps cifs uid=[value of id -u],gid=[value of id -g],user=[username for your NAS],password=[password for your NAS] 0 0
````
`````
e.g. //truenas.local/games/steam/steamapps /home/user/.local/share/Steam/steamapps cifs uid=1000,gid=1001,user=exampleuser,password=supersecret 0 0
`````


press `ctrl + x`

press `y`

press `enter`

### Now enter the following in your terminal

````
sudo mount -a
````

and 

````
systemctl daemon-reload
````

### Congratulations! You have now linked your SteamLibrary on your NAS with your Steamlibrary on your PC.
