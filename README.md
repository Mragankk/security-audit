# SOLIDITY AUDIT
## Environment setup
### docker-install


#### Quick Install
```bash
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```
---

install packages:
```bash
sudo apt update
sudo apt install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release \
    jq
```

Add Docker’s official GPG key:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
#### SEE IMGAGES/INSPECT
```bash
 docker images
```
```bash
 docker inspect
```
```bash
  docker ps
```

## Security Audits for Solidity
- Solgraph : `docker pull devopstestlab/solgraph`
  
### Solgraph Steps
- Create a directory `mkdir data`
- Create a sol file `MyContract.sol`
- Run solgraph :
``` sh
docker run -it --rm -v $PWD:/data devopstestlab/solgraph
```
Output will be the file name i.e. MyContract.sol

To view the successfully generated Graph-
```
xdg-open MyContract.sol.png
```
