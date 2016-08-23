Vagrant.configure(2) do |config|
  config.vm.box = "bento/ubuntu-14.04"
  config.vm.hostname = "alchemist" 

  # Use an inline shell provisioner for basic setup 
  config.vm.provision 'shell', inline: shell, privileged: false
  
  # Support for Phoenix on the VM 
  config.vm.network "forwarded_port", guest: 4000, host: 4000, id: "phoenix"
end

def shell
  <<-eos
    echo Installing basic tools and create temporary directory
    sudo apt-get update
    sudo apt-get -y install vim git-core 

    echo Installing erlang to support Elixir
    wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
    sudo apt-get update
    sudo apt-get -y install esl-erlang

    echo Installing Elixir
    sudo apt-get -y install elixir

    echo Installing Hex
    mix local.hex --force 

    echo Installing Phoenix
    mix archive.install --force https://github.com/phoenixframework/archives/raw/master/phoenix_new.ez

    echo Installing Tmux
    sudo apt-get -y install tmux

    echo Installing Tree
    sudo apt-get -y install tree

    echo Installing Curl
    sudo apt-get -y install curl

    echo Cloning Dot Files
    cd ~
    git clone https://github.com/hogihung/dotfilez.git
  eos
end
