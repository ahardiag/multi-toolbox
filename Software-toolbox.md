# General Software Toolbox for Linux

<!-- TOC -->

- [General Software Toolbox for Linux](#general-software-toolbox-for-linux)
    - [Conda](#conda)
        - [Look for a package in all conda environments](#look-for-a-package-in-all-conda-environments)
    - [NextCloud](#nextcloud)
    - [Latex](#latex)
        - [Latex distribution](#latex-distribution)
        - [On VSCode](#on-vscode)
    - [Github](#github)
        - [Save a token password key](#save-a-token-password-key)
        - [Deposit of a source code on HAL](#deposit-of-a-source-code-on-hal)
    - [Zotero](#zotero)
        - [Backup/Restore Zotero](#backuprestore-zotero)
        - [Repair sqlite](#repair-sqlite)
    - [Google Drive on linux architecture](#google-drive-on-linux-architecture)
        - [Via Google-drive-ocamlfuse](#via-google-drive-ocamlfuse)
    - [VSCode](#vscode)
        - [Useful extensions](#useful-extensions)
        - [Shortcuts](#shortcuts)
            - [Overview of principal keyboard shortcuts :](#overview-of-principal-keyboard-shortcuts-)
        - [Markdown](#markdown)
            - [Preview markdown on the right side](#preview-markdown-on-the-right-side)
            - [Extensions :](#extensions-)
            - [Image centered with caption :](#image-centered-with-caption-)
    - [Tcl-VMD toolbox](#tcl-vmd-toolbox)
            - [Render in png format with tachyon](#render-in-png-format-with-tachyon)
            - [Render a snapshot](#render-a-snapshot)
        - [Crop an image](#crop-an-image)
            - [Operations on list](#operations-on-list)
            - [Wrap a selection](#wrap-a-selection)
            - [draw a dashed line between two atoms and a measure distance](#draw-a-dashed-line-between-two-atoms-and-a-measure-distance)
    - [Inkscape](#inkscape)
    - [VPN](#vpn)
            - [Open a jupyter notebook from a remote server:](#open-a-jupyter-notebook-from-a-remote-server)
            - [List jupyter notebooks servers open :](#list-jupyter-notebooks-servers-open-)
            - [Delete a jupyter server :](#delete-a-jupyter-server-)
            - [Delete all jupyter servers and possible crashed servers :](#delete-all-jupyter-servers-and-possible-crashed-servers-)
            - [Use VPN on Debian 10 machine sirius](#use-vpn-on-debian-10-machine-sirius)
    - [Movie converter](#movie-converter)
            - [Decrease size of a movie and convert format](#decrease-size-of-a-movie-and-convert-format)

<!-- /TOC -->

## Conda

### Look for a package in all conda environments
```Bash
conda search <package> --envs
```

## NextCloud
Works in Ubuntu 18.04 :
```Bash
sudo add-apt-repository ppa:nextcloud-devs/client
sudo apt install nextcloud-client nextcloud-client-nautilus
sudo apt install nextcloud-desktop
```

## Latex 
### Latex distribution
```Bash
sudo apt install texlive-full -y # Heavy 5Go
sudo apt install texlive -y # Lighter 200 Mo
```

### On VSCode
Need extension `̀LateX Workshop`
To build the current project : `CTRL`+ `L` `B` 

## Github

### Save a token (password key)
```Bash
git config --global credential.helper cache
```
It must be done after using a git command and given explicitly the token

### Deposit of a source code on HAL
How to ?
Slides:
https://hal.archives-ouvertes.fr/hal-01872189

Website version:
https://doc.archives-ouvertes.fr/deposer/deposer-le-code-source/

List of Licences :
https://spdx.org/licenses/

## Zotero

### Backup/Restore Zotero
https://aut.ac.nz.libguides.com/zotero/backup

### Repair sqlite
https://www.zotero.org/utils/dbfix/
- Do a backup of Zotero
- Close Zotero
- Upload .sqlite file
- Download the new .sqlite file and replace teh old one in the Zotero folder
- Restart Zotero

## Google Drive on linux architecture

### Via Google-drive-ocamlfuse
https://doc.ubuntu-fr.org/google_drive#google-drive-ocamlfuse

## VSCode

### Useful extensions
- **Dataflex Colorize** : ??? do not know why it is installed
- **vscode-pdf** : visualize pdf
- **Spell Right** : orthographic corrector
    To link linux langages dictionaries to VSCODE :
    ```bash
    ln -s /usr/share/hunspell/* ~/.config/Code/Dictionaries
    ```

### Shortcuts
1) File -> Preferences -> Keyboard Shortcuts
2) Look for a specific command ,e.g. :
- shortcut to move from editor to terminal: `Focus Terminal`
my personal choice : `ALT`+ `T` 
- shortcut to move to first panel editor: `First Editor` 
my personal choice : `ALT`+ `E` 

#### Overview of principal keyboard shortcuts :
https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf

### Markdown

#### Preview markdown (on the right side)
After enaling a previewer like Markdown Preview Enhanced
`CTRL+K` `V`

#### Extensions :
- **Markdown Preview Enhanced** : preview of markdown
- **Markdown PDF** : to convert onin pdf format
- **Auto Markdown TOC** : to create table of Contents
- **Markdown Table** : to manipulate tables

#### Image centered with caption :
```html
<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](snap_f1_cylinder_zoom.png)
</div><figcaption>Figure 11 </figcaption></figure>
```

## Tcl-VMD toolbox

#### Render in png format with tachyon
```Tcl
render Tachyon myfigure  "/usr/local/lib/vmd/tachyon_LINUXAMD64" -aasamples 12 %s -format BMP -res 2400 2146 -o %s.bmp
convert myfigure.bmp myfigure.png
```

#### Render a snapshot
```Tcl
set filename path_to_file
render snapshot $filename.tga
convert $filename.tga $filename.png -quality 10%
```

### Crop an image
```Bash
convert filename.bmp  -crop 1680x1600+380+290 filename.png
```

#### Operations on list 
```Tcl
vecaad
vecsub
vecinvers
```

#### Wrap a selection
```Tcl
pbc wrap -compound "residue"
```

#### draw a dashed line between two atoms and a measure distance
Menu `Mouse-> Lables->Bond(2)`
Or
` ALT`+`2`
Or `2` on the Numeric Pad
The second method allows to pass from one mouse menu to another (`ALT`+`1`, `ALT`+`2`,...)

## Inkscape
To add the lateral scroll : CTRL-B


## VPN
Method to add a VPN from .ovpn file using OpenVPN:

Télécharger le fichier personnalisé ovpn en suivant le lien du wiki et supprimer la ligne 7 (route remote_host 255.255.255.255 net_gateway) et renommer en username.ovnp puis en ligne de commande :
```Bash
sudo apt-get install network-manager-openvpn-gnome openvpn-systemd-resolved
sudo nmcli connection import type openvpn file <username.ovpn>
```
Après cette étape, tu peux déjà essayer de voir si tu as un icône VPN dans les paramètres Réseau, l'activer, et voir si tu arrives à ouvrir le wiki hébergé sur le réseau. Si la page s'affiche, ça marche !
Sinon, ça se peut que les adresses du réseau ne soient pas bien reconnus par ton FAI, du coup essaie cela également :
Commenter toutes les lignes dans /etc/hosts qui concernent IPv6 ($ sudo vim /etc/hosts) puis :
```Bash
sudo mv /etc/resolv.conf{,.orig}
sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf
```
Puis ajouter manuellement les DNS de google sur la connection (filiaire ou wifi) sur le GUI NetworkManager Paramètre-> Réseau->roue dentée):
<figure align="center"><div style="text-align:center; width:500px;margin: 0 auto">

![Legende](vpn1.png)
</div><figcaption>Figure 11 </figcaption></figure>
```Bash
sudo nmcli networking off
sudo nmcli networking on
```
Activer le VPN dans le GUI NetworkManager (sur gnome seulement), puis aller chercher le nom de la connexion à travers VPN, généralement tun0
```Bash
nmcli connection show
nmcli connection modify <nom de connexion> ipv4.never-default true
```
La tu peux essayer de nouveau de rentrer sur le wiki, ou pinger une adresse du réseau, par exemple:
```Bash
ping toto.lbt.ibpc.fr
```

Activate VPN once installed :
Activer le VPN dans le GUI NetworkManager (sur gnome seulement), puis aller chercher le nom de la connexion à travers VPN, généralement tun0
```Bash
nmcli connection show
nmcli connection modify <nom de connexion> ipv4.never-default true
```
Activer manuellement le VPN dans le menu en haut à droite, éventuellement en donnant le mot de passe 
<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](vpn2.png)
</div><figcaption>Figure 11 </figcaption></figure>


#### Open a jupyter notebook from a remote server:

- Go to remote server and open the jupyter notebook in the working directory:
```Bash
jupyter notebook --no-browser --port 9999
```
Or to avoid closing the jupyter notebook if the terminal is close or connection stopped
```Bash
nohup jupyter notebook --no-browser --port 9999 & disown
```
- Open a tunnel SSH in local to be able to open the notebook in the local web browser:
```Bash
ssh -NL 9999:localhost:9999 <Host>
```
Remark : 
Host must be defined in .ssh/config
If the terminal is closed, the connection is lost, but thesame jupyter notebook can be reached by opening it the connection.

- Lauch in a we browser by typing localhost:9999/
A password is sometimes needed

#### List jupyter notebooks servers open :
```Bash
jupyter notebook list
```

#### Delete a jupyter server :
```Bash
jupyter notebook stop 9999
```

#### Delete all jupyter servers and possible crashed servers :
```Bash
rm -i /home/hardiagon/.local/share/jupyter/runtime/*
```

#### Use VPN on Debian 10 (machine sirius)
```Bash
# Activate VPN 
nmcli connection up hardiagon
# Disable IPV4 connections
vpn_id=$(nmcli connection show | grep tun0 | head -n 1 | awk '{print $2}')
nmcli connection modify $vpn_id  ipv4.never-default true
# Test both webserver and remote server
ping google.fr -w 3
ping toto.lbt.ibpc.fr -w 3
```

Rk : To do it automatically,  one can write this on a script called vpn which path is visible by the system.



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwNjE4NTM0Ml19
-->


## Movie converter

#### Decrease size of a movie and convert format 
Reduce duration :
```Bash
ffmpeg -i movie_H01_pure_water_C770.mpg -ss 10 -fs  10000000    movie_H01_pure_water_C770.mp4
```
Change the frame format :
```Bash
ffmpeg -i input.mp4 -vf scale=1280:720 output.mp4
```
Simple Commands :
https://opensource.com/article/17/6/ffmpeg-convert-media-file-formats
https://www.winxdvd.com/resize-video/compress-video-with-ffmpeg.htm
Documentation : https://ffmpeg.org/ffmpeg.html#Audio-Options