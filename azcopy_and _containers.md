### Setup azcopy on Ubuntu
```
cd ~
wget https://aka.ms/downloadazcopy-v10-linux
tar -xvf downloadazcopy-v10-linux
cd azcopy_linux_amd64_10.8.0/
sudo cp azcopy /usr/bin/
sudo chmod 755 /usr/bin/azcopy
azcopy --version
```
