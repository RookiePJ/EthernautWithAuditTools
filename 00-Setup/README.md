
### Setup Auditing tools

#### Ethereum Security Toolbox from Trail of Bits (https://github.com/trailofbits/eth-security-toolbox)

Install using docker:

    docker pull trailofbits/eth-security-toolbox

Mount the current directory as /project [-v] and then start an command shell [-it]:

    docker run -it -v $(pwd):/home/ethsec/project trailofbits/eth-security-toolbox

Run slither on Fallback.sol from the project home directory:

    docker run -v $(pwd):/home/ethsec/project trailofbits/eth-security-toolbox -c "slither /home/ethsec/project/contracts/Fallback.sol"

Run Echidna on Fallback.sol:

    docker run -v $(pwd):/home/ethsec/project \ 
    trailofbits/eth-security-toolbox  \
    -c "echidna-test --format text /home/ethsec/project/contracts/Fallback.sol"

Run Manticore (maybe)

#### Mythril from Consensys (https://github.com/ConsenSys/mythril)

Install using docker:

    docker pull mythril/myth

Run mythril on the Fallback.sol contract:

    docker run -v $(pwd):/tmp \ 
    mythril/myth analyze /tmp/contracts/Fallback.sol

#### Scribble from Consensys

Install scribble locally:

    npm install -g eth-scribble

Run scribble to print installed version: 

    scribble -v 


References;
https://mythril-classic.readthedocs.io/en/master/about.html
https://mixbytes.io/blog/guide-smart-contract-security-tools-mythril
https://curatedpython.com/p/slither-the-crytic-slither/index.html
https://docs.scribble.codes/

