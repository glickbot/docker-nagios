## Docker-Nagios
Basic Docker image for running Nagios.<br />
This is running Nagios 4.0.8

You should either link a mail container in as "mail" or set MAIL_SERVER, otherwise
mail will not work.

### Knobs ###
- NAGIOSADMIN_USER=nagiosadmin
- NAGIOSAMDIN_PASS=nagios

### Web UI ###
The Nagios Web UI is available on port 80 of the container<br />

### Example usage ###
    ls ./
        configure.sh
        commands.cfg
    
    cat configure.sh
        #!/bin/bash
        script_path=$( cd "$( dirname "$0" )" && pwd )
        cp ${script_path}/commands.cfg /opt/nagios/etc/objects/

    docker run -d --name nagios
    docker run --rm -v $(pwd):/tmp --volumes-from nagios --entrypoint /tmp/configure.sh cpuguy83/nagios

### Credits ###
* [cpuguy83](https://github.com/cpuguy83/docker-nagios)
* [zachberger](https://github.com/zachberger/docker-nagios)
* [jandahl](https://github.com/jandahl/docker-nagios)
* [tpires](https://github.com/tpires/docker-nagios)

