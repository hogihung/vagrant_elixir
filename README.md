# README - Vagrant Based Elixir & Phoenix Development VM

This repo was built to have a nice way for one to try out Elixir and Phoenix
without having to install those tools on their computer.  As long as you have
Vagrant working you should be good to go.

Batteries are not included, but the following is:

* Ubuntu 14.04 64-bit (based off of the box: "bento/ubuntu-14.04"
* Elixir  1.3.2
* Phoenix 1.2.0 
* Vim     7.4
* Tmux    1.8
* Curl    7.35.0
* Tree    1.6.0

First you will need to clone the repo:

```
cd /path/to/where/you/want/this (e.g. /home/jfhogarty/Documents/Vagrant_VMs/)
git clone xxxx
``` 

After you have cloned the repo, changed to the new directory it created and bring
up a new Vagrant based VM (virtual machine):

```
cd vagrant_elixir
vagrant up
```

After you run vagrant up and it builds your new environment, you need to connect
using the command:

```
vagrant ssh
```

Once logged in, we will confirm that Elixir has been installed:

```
elixir --version
mix --version


EXAMPLES:
vagrant@alchemist:~$ elixir --version
Erlang/OTP 19 [erts-8.0.2] [source-9503fff] [64-bit] [async-threads:10] [hipe] [kernel-poll:false]

Elixir 1.3.2
vagrant@alchemist:~$


vagrant@alchemist:~$ mix --version
Erlang/OTP 19 [erts-8.0.2] [source-9503fff] [64-bit] [async-threads:10] [hipe] [kernel-poll:false]

Mix 1.3.2
vagrant@alchemist:~$
```

To do a quick test to make sure Phoenix was installed correctly, try the following:

```
cd ~
mkdir PHOENIX_APPS
cd PHOENIX_APPS
mix phoenix.new web --no-brunch --no-ecto
```


I've included my dotfiles repo mostly for my vim related settings/configuration.
If you want to use the same type of look and feel of vim that I have, and take
advantage of the plugins I use, see the Readme file at:

```
/home/vagrant/dotfiles/README.md 
```

