# Prepare Rails server with Chef Solo

## Prepare local environment

* Preferred way to use is to clone this repo and customise for your project
  `git clone git://github.com/fs/rails3-base-chef.git --origin upstream APPLICATION-NAME-chef`
* Bootstrap local environment with `script/bootstrap`

## Prepare server

* Setup key based authentication to the target host for example with `ssh-copy-id`
* Prepare target server with `script/prepare root@HOSTNAME`
* Customize `nodes/hostname.json`
* Apply configuration to target host with `script/cook user@HOSTNAME`

## Continue with Capistrano

Checkout [deploy branch of Rails3-Base](https://github.com/fs/rails3-base/tree/deploy)
and [deploy.rb](https://github.com/fs/rails3-base/blob/deploy/config/deploy.rb)
