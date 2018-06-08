# bolero.headless
A headless instance of [bolero.fun](https://github.com/SemkoDev/bolero.fun). This makes it very quick and easy to bootstrap new [IOTA IRI](https://github.com/iotaledger/iri) nodes on new machines.

# Installation
To install on a new machine:

    npm install -g bolero.headless

Then start with

    bolero.headless

## Installation on a Fresh AWS Instance

    sudo yum update -y
    sudo yum install git
    # Install nvm which installs node and npm without sudo
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash # from https://github.com/creationix/nvm#install-script
    # Download compatible JDK rpm from http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
    # Upload to box with Filezilla or scp
    sudo rpm -i jdk-8u172-linux-x64.rpm
    # reopen terminal
    npm install -g bolero.headless

# Run with

    bolero.headless

## Run in the background

    nohup bolero.headless > /dev/null 2>&1 &

And tail logs with

    tail -f ~/.bolero/current.log