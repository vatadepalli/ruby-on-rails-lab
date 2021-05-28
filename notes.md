# README

## Setup

1.  Change shell to ZSH

        chsh -s /bin/zsh

2.  Installing Homebrew

        ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

3.  Install **_rbenv_** & add it to zsh

        brew install rbenv ruby-build
        echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
        source ~/.zshrc

4.  Install Ruby

        rbenv install 3.0.1
        rbenv global 3.0.1
        ruby -v

5.  Config Git

        git config --global color.ui true
        git config --global user.name "YOUR NAME"
        git config --global user.email "YOUR@EMAIL.com"

        ssh-keygen -t rsa -C "YOUR@EMAIL.com"
        cat ~/.ssh/id_rsa.pub

        ssh -T git@github.com

6.  Install Rails

        gem install rails -v 6.1.3.2

        # To make rbenv to see rails
        rbenv rehash

        rails -v

7.  Setting up DB

        # To use SQLite3
        brew install sqlite3

        # Alternatively Setup Postgres
        # Default credentials - current OS X username & no password

        brew install postgresql
        brew services start postgresql

8.  Final

    -   To Install pg, nokogiri or other stuff that require C extensions

            sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /

## Creating a new app

    rails new myapp
    rails new myapp -d mysql
    rails new myapp -d postgresql

    # Modify the config/database.yml - with username and password

    cd myapp
    rake db:create
    rails server

    # http://localhost:3000
