# Install Node.js
## Process:
1. Install node.js
2. Install npm (manage node.js package)

---
## Ubuntu
### 1. Upgrade libuv1
libuv1 is old version, we can't use apt-get install nodejs. 

Solution: add libuv1 apt-get repository.
```sh
sudo add-apt-repository ppa:acooks/libwebsockets6
```
### 2. Add npm apt-get repository
```sh
sudo add-apt-repository ppa:gias-kay-lee/npm
```
### 3. Install All
```sh
sudo apt-get update 
sudo apt-get install libuv1
sudo apt-get install nodejs
sudo apt-get install npm
```
---
## CentOS / RedHat
### 
```sh
curl --silent --location https://rpm.nodesource.com/setup_10.x | sudo bash -
sudo yum -y install nodejs
```
### Optional
To compile and install native addons from npm you may also need to install build tools:
```sh
sudo yum install gcc-c++ make
# or: sudo yum groupinstall 'Development Tools'
```