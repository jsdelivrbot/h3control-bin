
UPDATE 22
- Fixed launchers (`h3control-console.sh` & `h3control-install-daemons.sh`)
- Building moved to github


UPDATE 21
- Improoved responsiblity of frequency control - gauges are updated immediately in response to click|tap on frequency. Intervals of refresh extended to `10s`.
- Dashboard is redesigned. All the widgets of dashboard fit on a tablet 1024x768 or above.
- Dashboard in disabled state (when orange pi is down) is also redesigned.
- Added swap utilization column to the list of the top memory usage list
- Added sorting choice for top processes list
- Fixed permissions inside h3control.tar.gz


UPDATE 19 (1.19.386)
- LESS colors, LESS gradients, LESS blur
- Added preliminary top process list


UPDATE 18 (1.18.310)
- Fixed support of Fedora and OpenSUSE in `./h3control-install-daemon.sh` script.
- Added info about mono and OS into logs.


UPDATE 17
- Added logging: log are writing into /tmp/h3control.logs/, /var/log/h3control.logs/ or /var/tmp/h3control.logs depending on permissions to that folder. h3control automatically trims own old logs.
- Added optional password protection of changing frequency. Screenshot: h3control_v1.17_readonly_mode.  How Dow do we do it? First, encrypt password:
````
    > ./h3control-console.sh -g=mySecret
    7D018BB3DF0E523692845AF1F27E992CE8A41650
````
Note, space before command above causes shell to eliminate the command from the history. By this way clear password will be stored nowhere. Finally, add parameter -p=7D018BB3DF0E523692845AF1F27E992CE8A41650 to h3control-console.sh or /etc/init.d/h3control daemon. For example:

````
    > ./h3control-console.sh -p=7D018BB3DF0E523692845AF1F27E992CE8A41650 -b=*:5000
````
Without -p option behavior is the same as prev version - anybody from white-list, or anybody, could change frequency of an Orange PI


UPDATE 16 (1.16.255)
- Server side redesigned. Samart cache improoved according to best practice recommendations (if-modified-since, etag).
- UI wasn't changed, Ctrl-F5 is still required after upgrade.
- [1.16.256] Cache of js and css was agressively improoved in comparision with 1.16.255
- Added bug: Icons for mobile browsers were lost. Fixed in 1.16.260

UPDATE 15 (1.15.239)
- Added 'Rate Me' and version number on the dashboard. Five Stars are welcome

UPDATE 14 (1.14.225)
- Added Memory Usage (Ctrl-F5). Compatiblity with old IE on Windows XP restored.

UPDATE 12
- CPU Usage bar was rearranged
- Warning: IE on Windows XP isnt supported since 1.12 Sorry for that. Please use Chrome or Firefox on Windows XP

UPDATE 11 (1.11.180)
- Improved UI perfomance (Ctrl-F5). Owners of old smartphones/tablets should prize this update

UPDATE 10 (1.10.172)
- Added update speed selector: 0.5s, 1s, 2s or 5s

UPDATE 9 (1.9.166)
- Dependencies (jquery, bootstrap) moved from the internet to h3control distribution. So h3control app works without the internet since 1.9.166

UPDATE 8 (1.8.151):
- Added CPU usage bar. (Ctrl-F5)
- Fixed CPU usage bar for old IE (1.8.161)

UPDATE 7 (1.7.116):
- Fixed the vaule of the DDR RANGE
- Added web app icons for mobile & desktop browsers

UPDATE 6.1:
- Added H3 icon for desktop and mobile browsers

UPDATE 6:
- Added versioning during build. Current version is 1.6.102.
- Added h3control-install-daemon.sh to the tarball, default deployment path of the daemon is $HOME/bin/h3control
- Improved handling of
    > /etc/init.d/h3control stop


UPDATE 5:
- Added 60 Mhz choice of a frequency

UPDATE 4: Added command line parameters of http server and ip's white-list configuration:
````
~>./h3control-console --help
    -b, --binding=VALUE         HTTP binding, e.g. ip:port, default is *:5000
    -w, --white-list=VALUE      Comma separated IPs, default or empty arg turns restrictions off
    -v, --version               Show version
    -h, -?, --help              Display this help
    -n, --nologo                Hide logo
````

UPDATE 3:
- Control CPU frequency

UPDATE 2: 
- Added user defined limits of CPU & DDR frequency

FIRST Version:
![first version](https://github.com/devizer/h3control-bin/raw/master/images/h3control-first.jpg   "h3control first version")