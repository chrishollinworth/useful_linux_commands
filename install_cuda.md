# Install CUDA on Ubuntu 21.10

## Blacklist Nouveau nvidia driver
`sudo bash -c "echo blacklist nouveau > /etc/modprobe.d/blacklist-nvidia-nouveau.conf"`

`sudo bash -c "echo options nouveau modeset=0 >> /etc/modprobe.d/blacklist-nvidia-nouveau.conf"`

` sudo update-initramfs -u`
## Purge Old Drivers

`sudo apt-get purge *nvidia*`

`sudo apt autoremove`

#### Or

`sudo /usr/bin/nvidia-uninstall` (For manaully installed driver)

#### Finally

`dpkg -l *nvidia*` (Check no old versions exist)

## Install Distribition Based GPU Driver

`sudo apt install nvidia-driver-510`

`reboot`

## Install CUDA Tookkit

`wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-ubuntu2004.pin`

`sudo mv cuda-ubuntu2004.pin /etc/apt/preferences.d/cuda-repository-pin-600`

`sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/3bf863cc.pub`

`sudo add-apt-repository "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/ /"`

`sudo apt-get update`

`sudo apt-get -y install cuda`

`reboot`
