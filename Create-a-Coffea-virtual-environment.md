# Create a Coffea virtual environment

### Install `conda`
We recommend creating a virtual environment with Coffea run Coffea-based code in this repository. `conda` is already installed on `lxplus` machines, but this is not the case at `t3ui01.psi.ch`         
If you need to install `conda`, go to https://conda.io/projects/conda/en/latest/user-guide/install/linux.html#installing-on-linux and follow instructions there. At PSI T3, because your home has limited storage, you can install `conda` in `/work/<username>/anaconda3`.

### Create virtual environment
```bash
prefix=<path_to_where_you_want_to_install_the_virtual_env>
conda create --prefix ${prefix} python=3.6
conda activate ${prefix}
conda install -c conda-forge root   # If you also need/want to have ROOT in your virtual env
conda install -c conda-forge coffea
conda install -c conda-forge xrootd # If you need/want xrootd in your virtual env
```
Important: on `lxplus` `conda` may complain a bit about non-existing or unaccessible directories - patiently create these directories and change permissions as advised by `conda`. It should work.