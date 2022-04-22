# oc-wrapper
A simple wrapper script for `oc` binary that:

- Logs all calls to a log file
- Intercept any `delete` command, show a `--dry-run=client` output of the delete command and get a confirmation before executing the actual delete command.

To install this wrapper script:

- Clone this repository and cd into the repository directory:
    ~~~
    # git clone https://github.com/kxr/oc-wrapper
    # cd oc-wrapper
    ~~~

- Create a log file and mark it writable as all users. For example:
    ~~~
    # sudo touch /var/log/oc.log
    # sudo chmod 666 /var/log/oc.log
    ~~~
- Set the log file in the wrapper script (oc) present in this repositry. For example:
    ~~~
    # vim ./oc
    ...
    LOGFILE="/var/log/oc.log"
    ...
    ~~~
- Move the original `oc` binary to any location that is not in `PATH`. For example:
    ~~~
    # mv $(which oc) /opt/
    ~~~
- At this point `oc` command should not work. For example:
    ~~~
    # oc
    bash: oc: command not found...
    ~~~
- Set the location of the original `oc` binary in the wrapper script (oc) present in this repository. For example:
    ~~~
    # vim ./oc
    ...
    OC_CMD="/opt/oc"
    ...
    ~~~ 
- Place the `oc` wrapper script present in this repository in a location that is in `PATH`. For example:
    ~~~
    cp ./oc /usr/bin/
    chmod +x /usr/bin/oc
    ~~~


Demo:
