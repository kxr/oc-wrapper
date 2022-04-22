# oc-wrapper
A simple wrapper script for `oc` binary that:

- Logs all calls to a log file
- Intercept any `delete` command, show a `--dry-run=client` output of the delete command and get a confirmation before executing the actual delete command.

To install this wrapper script:

- Move the origina `oc` binary to any location that is not in `PATH`. For example `/opt/oc`
- Set the location of the original `oc` binary in the wrapper script (`oc`) present in this repository. For example `OC_CMD="/opt/oc"` 
- Place the `oc` wrapper script present in this repository in a location that is in `PATH`. For example `/usr/bin/oc`


Demo:
