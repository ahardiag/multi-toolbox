
# VSCODE
## Compile C code using Vscode
https://code.visualstudio.com/docs/cpp/config-mingw

# Mount remote file system
https://github.com/winfsp/sshfs-win

# Internet Connection
## Find the mac adress of an ethernet adapter
Settings->Network & Internet->Advances Nework settings->Hardware and Connection properties
Or on a powershell :
```
ipconfig /all
```

# Owncloud 
### Client
## Add an account 
- Download the last version of the client : https://owncloud.com/desktop-app
- Connect in the web server : https://mycore.core-cloud.net
- Got to Paramètres -> Demander  de Créer un nouveau mot de passe
- Connect to the client using email adress and the password you just have defined

### Webdav
tutorial : https://doc.owncloud.com/webui/next/classic_ui/files/access_webdav.html#mapping-drives-with-windows-explorer
This is nice when synchronization with Ownclient bugs (quite often I noticed), but i requires a good connexion since the data is not stored in local and based on Owncloud web server requests.

# VMD
Install VMD version Version 1.9.4 LATEST ALPHA (2022-04-27) on Windows 11 : 
1) Download and instal vmd
2) Create an environment variable to avoid error dur to OPSRAY : https://www.ks.uiuc.edu/Research/vmd/mailing_list/vmd-l/34008.html
