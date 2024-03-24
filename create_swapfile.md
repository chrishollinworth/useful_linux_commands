# resize swap file and Enable Hibernate on Swap File:

sudo swapoff -a 
sudo rm /swapfile 
sudo fallocate -l 64G /swapfile 
sudo chmod 600 /swapfile 
sudo mkswap /swapfile 
sudo swapon /swapfile 

echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

# check UUID
blkid

# find offset (row 0 3rd column)
sudo filefrag -v /swapfile

add UUID and offset to /etc/default/grub

sudo gedit /etc/default/grub

add resume=UUID=xxx resume_offset=xxx as value of “GRUB_CMDLINE_LINUX_DEFAULT”.
sudo update-initramfs -c -k all