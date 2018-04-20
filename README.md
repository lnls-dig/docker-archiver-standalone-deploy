# Docker compose for EPICS archiver with plug-and-play configurations

## Setup

As we are running the containers in network_mode = "host",
we need to add the mysql-db address to our /etc/hosts
files:

    sudo bash -c 'echo "127.0.0.1   epics-archiver-mysql-db" >> \
        /etc/hosts'

Also, set the EPICS_CA_ADDR_LIST variable according to your
network. Just puts yout subnet broadcast and/or the IPs of
any machines running IOCs. The file is located in 
configuration/lnls-epics-archiver.env.

### Running instructions

    ./run-archiver.sh

The webpage should be available at:

	http://localhost:11995/mgmt/ui/index.html

### Stopping instructions

    ./stop-archiver.sh
