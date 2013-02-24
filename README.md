# Prepare Rails server with Chef Solo


* Preferred way to use is to clone this repo and customise for your project 
  `git clone git://github.com/fs/application-chef.git --origin upstream my-application-name-chef`
* Bootstrap local environment with `script/bootstrap`
* Setup key based authentication to the target host for example with `ssh-copy-id`
* Prepare target server with `script/prepare user@hostname`
* Customize `nodes/hostname.json`
* Apply configuration to target host with `script/cook user@hostname`
