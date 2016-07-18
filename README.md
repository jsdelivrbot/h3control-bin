
# h3control-bin [![travis status](https://travis-ci.org/devizer/h3control.svg?branch=master)](https://travis-ci.org/devizer/h3control)  <img src='https://github.com/devizer/h3control-bin/blob/master/public/status.png?raw=true' width='199' height='32' style='float: right' alt='public' title='public'></img><img src='https://github.com/devizer/h3control-bin/blob/master/staging/status.png?raw=true' width='199' height='32' style='float: right' alt='staging' title='staging'></img>
h3control is a console/daemon for H3 based PI board. It displays temperature, frequency and usage via built-in http server. It allows to control min/max cpu and ddr frequency. This repository holds installers of h3control only

## prerequisite
The only prerequisite is mono with .NET 4.5 runtime. By the way, first mono (version 3.2), which supports ARM hard float arch, exposes .NET 4.5 runtime.

## launch using `h3control-console.sh`
Step 1: wget & run the *latest* h3control-console.sh
```bash
wget -q -O - https://github.com/devizer/h3control-bin/raw/master/public/h3control.sh | bash
```

Step 2: Switch to your `Firefox` | `Chrome` | `IE` | `Opera` | `Safary`, and check http://orange-pi-address:5000/ works fine. 

Step 3: Return to your PI board and press Ctrl-C to stop consolas h3control. Install h3control daemon to start h3control during build
```
h3control/h3control-install-daemon.sh
```

## install/update h3control daemon (`PUBLIC` version)
```bash
wget -q -O - https://github.com/devizer/h3control-bin/raw/master/public/h3control-install-daemon.sh | bash
```
this command downloads public version of h3control into `$HOME/bin/h3control`, configures to start h3control during boot and start it after all. By the way, script h3control-install-daemon.sh is included into h3control.tar.gz distribution

## launch h3control in console (~~STAGING~~ version)
```bash
wget -q -O - https://github.com/devizer/h3control-bin/raw/master/staging/h3control-staging.sh | bash
```
this command downloads staging version of h3control into `**/tmp/h3control**`, and starts that staging version after all. This command doesnt affects preinstalled h3control daemon. You can press Ctrl-C and return to preinstalled early h3control daemon using '/etc/init.d/h3control start'
Usually staging version works fine, but it MAY not be tested by me.




<a name="screenshots"></a>
### Screenshot: h3control just works
![h3control in normal](https://github.com/devizer/h3control-bin/raw/master/images/h3control_v1.21_normal.jpg "h3control in normal")


### Screenshot: h3control in readonly mode
![h3control in readonly mode](https://github.com/devizer/h3control-bin/raw/master/images/h3control_v1.21_readonly.jpg "h3control in readonly mode")


### Screenshot: h3control is offline
![h3control is offline](https://github.com/devizer/h3control-bin/raw/master/images/h3control_v1.21_offline.jpg "h3control is offline")

### Screenshot: first version 0.1, not available now
<center><img src='https://github.com/devizer/h3control-bin/raw/master/images/h3control-first.jpg' alt='h3control first build' border='0' width='840px' height='541px' style='width:840px; height:541px'></img></center>
