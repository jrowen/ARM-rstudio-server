# ARM-rstudio-server
Build script for rstudio-server on an ARM Chromebook

This is built on the excellent work of [dashaub/ARM-RStudio](https://github.com/dashaub/ARM-RStudio).

## Build
This script has been used to successfully build RStudio Server on an Acer CB5-311 Chromebook (ARM) running Debian 9 (stretch) via [crouton](https://github.com/dnschneid/crouton).  The commands below can be used to build the server
```
sudo enter-chroot -n stretch
sudo croutonpowerd -i ./build_rstudio.sh
```
The build may take several hours to complete, and to prevent the Chromebook from suspending, it's recommended to use `crountonpowerd -i` and be plugged into AC power when running the build script.

The `VERS` variable in the script can be updated to build different versions of the server.  The latest version number and be found on the rstudio server [download page](https://www.rstudio.com/products/rstudio/download-server/).

## Launching RStudio Server
After the server has been built and installed, the easiest way to start the server from a crosh shell using the commands below
```
sudo enter-chroot -n stretch
sudo rstudio-server start
```
From a new Chrome tab navigate to `localhost:8787` and log in using your chroot credendials.
