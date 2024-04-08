# SOLIDITY AUDIT
## Environment setup
### docker-install

https://hub.docker.com

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
![image](https://github.com/Mragankk/solidity-audit/assets/145200189/6a813bd6-f2c2-4b95-8642-b848f5a5b1f1)

-Slither: `docker pull trailofbits/eth-security-toolbox`

### Slihter steps
-  Create a directory ```mkdir Audit```
- Create a sol file ```vi SimpleStorage1.sol```
- Pull Docker Image for slither : `docker pull trailofbits/eth-security-toolbox`
- Run : `docker run -it -v $PWD:/Audit trailofbits/eth-security-toolbox `     [ $PWD:/Audit is the path to the file ]

  ![image](https://github.com/Mragankk/solidity-audit/assets/145200189/47d37bfc-f981-425b-b55b-1ce4616602c7)

- open a new terminal, run the command `docker ps` to see the list of id's.
- then use the command `sudo docker cp $(pwd)/MyContract.sol 1735b05a0022:/home/ethsec` to copy the file to docker file

![image](https://github.com/Mragankk/solidity-audit/assets/145200189/1ab8f27b-658d-4dbf-9525-54209b0462a0)

  2nd Command to check the ERC-20 token status of your contract - 
```
slither-check-erc MyContract.sol Persssist
// if you are using any other MyContract file then instead of "Persssist" add the contract name in the file
```

![image](https://github.com/Mragankk/solidity-audit/assets/145200189/bd04f0fe-43d6-4033-86b2-95bf8f30255f)

- Mythril : `docker pull mythril/myth`
