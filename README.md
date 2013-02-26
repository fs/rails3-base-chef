# Prepare Rails server with Chef Solo


## Prepare local environment

* Preferred way to use is to clone this repo and customise for your project 
  `git clone git://github.com/fs/application-chef.git --origin upstream APPLICATION-NAME-chef`
* Bootstrap local environment with `script/bootstrap`

## Prepare server

* Setup key based authentication to the target host for example with `ssh-copy-id`
* Prepare target server with `script/prepare root@HOSTNAME`
* Customize `nodes/hostname.json`
* Apply configuration to target host with `script/cook user@HOSTNAME`

## Continue with Capistrano

```ruby
require "bundler/capistrano"

server "HOSTNAME", :web, :app, :db, primary: true

set :user, "deployer"
set :application, "APPLICATION_NAME"
set :deploy_to, "/var/www/#{application}"
set :deploy_via, :remote_cache
set :use_sudo, false

set :scm, "git"
set :repository, "git@github.com:fs/#{application}.git"
set :branch, "develop"

default_run_options[:pty] = true
ssh_options[:forward_agent] = true

set :default_environment, {
  'PATH' => '/opt/rbenv/shims:/opt/rbenv/bin:$PATH'
}

```

