
## CCDC

The CCDC allows to acess the CSD cristallographic database and provides proprietary softwares to handle the data either through graphical visualization software (like Mercury or ConQuest) or through the python API.

### CCDC suite
First, download the CCDC suite at :
https://www.ccdc.cam.ac.uk/support-and-resources/csdsdownloads/
You need to provide :
- your email : the one that you provide when signing in into CCDC website
- the Customer Number
- the Activation Key
You will receive an email with 24h links to download CSD softwares. Install the "CSD Portfolio 2023.1 Linux Offline Installer (18 GB)". On Ubuntu 22.04, the python API may return some errors due to missing dependencies. Still the CSD database will be present locally, and you will have access to softwares like Mercury, ConQuest, or GOLD.

To properly install the python API, one can use Conda through the following procedure.

### CSD Python API

Source : https://fd-test.ccdc.cam.ac.uk/media/Documentation/1DBA2AB9-9DC7-423C-8EC9-9291D9C220DA/2020_CSD_Python_API_installation.pdf
* Create a conda environment with `python=3.7`
* Add the `conda-forge` channel
* Install using the absolute path where the ccdc API is laocated (downloaded through the entire suite as mentionned above)
* Let your system read the installation paths
```Bash
conda create -n csd-python-api python=3.7 
conda config --add channels conda-forge
conda config --set channel_priority strict
conda install -c /opt/CCDC/Python_API_2022/ccdc_conda_channel csd-python-api
conda env config vars set CSDHOME=/opt/CCDC/CSD_2022
```

> NOTE : solving the environment can take a few minutes due to the number of dependencies to satisfy.

Test it in a python shell:
```Python
import ccdc
import ccdc.io
import ccdc.search
print("ccdc.__version__", ccdc.__version__)
print("ccdc.io.csd_directory()", ccdc.io.csd_directory())
print("ccdc.io.csd_version()", ccdc.io.csd_version())

from pathlib import Path
subset_mofs_all = Path(ccdc.io.csd_directory()) / "subsets" / "CSD_MOF_subsets/MOF_subset.gcd"
print(f"Number of MOFs: {len(ccdc.io.EntryReader(str(subset_mofs_all)))}")
``` 