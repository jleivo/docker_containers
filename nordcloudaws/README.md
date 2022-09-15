# Accessing Nordcloud hosted AWS
Nordcloud AWS is behind SAML authentication, which is done against Azure

## prerequisites
* docker

## Building an image
1. clone repository XX
2. build nordcloudaws \
docker build -t nordcloudaws .

## Installation
1. copy helper script awsnord from git repo \
sudo cp scripts/awsnord /usr/local/bin
2. grant running rights \
sudo chmod a+x /usr/local/bin/awsnord
3. create configuration files and folders\
touch ~/.saml2aws \
mkdir ~/.aws \
touch ~/.aws/config
touch ~/.aws/credentials

## First usage
Run configuration for the saml2aws program\
nordaws configure\
? Please choose a provider: **ADFS**\
? Please choose an **MFA Auto**\
? AWS Profile **saml**\
? URL **https://az2sts.kone.com/adfs/ls/IdpInitiatedSignon.aspx**\
? Username **<first.lastname@kone.com>**\

## Usage
1. nordaws login
2. select correct profile
3. use aws cli as per normal