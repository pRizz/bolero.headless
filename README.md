# bolero.headless
A headless instance of [bolero.fun](https://github.com/SemkoDev/bolero.fun). This makes it very quick and easy to bootstrap new [IOTA IRI](https://github.com/iotaledger/iri) nodes on new machines.

# Before Installing

## Port Forwarding (from bolero.fun)

You also need to open ports (port forwarding) in your NAT Router:

* **UDP 14600**
* **TCP 15600**
* **TCP 16600**
* **TCP 21310**

Please refer to your Router's manual on how to do that.

Furthermore, if you launch your node at home, please be aware that apart of firewall and port-forwarding in
your router, your Internet provider may also be an issue. Some providers (like Vodafone in Germany) do not have enough IPv4 addresses and
thus use something called "**IPv4 over DS Lite**". In those cases the **traffic will not come through** over the ports
mentioned above. Unfortunately, there is no quick fix for this issue (maybe changing providers).
There is some hope with the upcoming PCP-protocol, this will not happen this year (2018) for most providers, though.

# Installation
To install on a new machine:

    npm install -g bolero.headless

Then start with

    bolero.headless

## Example Installation on a Fresh AWS Instance

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