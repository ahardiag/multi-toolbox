## NextCloud Client
Tested on Ubuntu 18.04, January 9th 2023:
Source : https://doc.ubuntu-fr.org/nextcloud-client
### Install Nextcloud using apt and PPA sources
```Bash
sudo add-apt-repository ppa:nextcloud-devs/client
sudo apt install nextcloud-client nextcloud-client-nautilus
sudo apt install nextcloud-desktop
```
Open the nexcloud client, and use the following server to log in: **`https://nextcloud.galaxy.ibpc.fr`**

<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](nextcloud_pictures/1.png)
</div></<figcaption></figcaption></figure>

An authentification page opens in your default brower to finish the client installation.

<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](nextcloud_pictures/2.png)
</div></<figcaption></figcaption></figure>

Return to the client and choose the path to the local folder taht you want to synchronize with the online server (e.g. : /home/username/Nextcloud).

<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](nextcloud_pictures/3.png)
</div></<figcaption></figcaption></figure>

<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](nextcloud_pictures/4.png)
</div></<figcaption></figcaption></figure>

The client should ressemble to the following :

<figure align="center"><div style="text-align:center; width:300px;margin: 0 auto">

![Legende](nextcloud_pictures/5.png)
</div></<figcaption></figcaption></figure>


### Uninstall all nextcloud packages and dependencies
```Bash
sudo apt purge nextcloud-client nextcloud-client-nautilus nextcloud-desktop
sudo apt --purge autoremove nextcloud-client nextcloud-client-nautilus nextcloud-desktop
```
