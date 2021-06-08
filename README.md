# tips-ubuntu

## Adjust the brightness of your screen.

First open a terminal with Ctrl + Alt + T
to find your monitor’s name, Type
```sh
xrandr | grep " connected" | cut -f1 -d " "
```
Now type 
```sh
xrandr --output your-monitor-name --brightness brightness-level
```
For example
```sh
$ xrandr | grep " connected" | cut -f1 -d " "
VGA1
$ xrandr --output VGA1 --brightness 0.7
```
In my case, the name of my monitor was VGA1 so, I used VGA1 as the monitor name and changed my brightness to 0.7.

<http://sandipbgt.com/2015/10/01/control-screen-brightness-from-commandline-in-ubuntu/>
 
## How do I fix my graphics driver Ubuntu?

Scenary: Screen with squares and issues visuals after upgrade from 18 - 20
Log into your account in the TTY.

Run 
```sh
sudo apt-get purge nvidia-*
```
```sh
sudo add-apt-repository ppa:graphics-drivers/ppa
```
and then 

```sh
sudo apt-get update .
```
```sh
sudo apt-get install nvidia-driver-430
```
> Reboot and your graphics issue should be fixed.

<https://askubuntu.com/questions/760934/graphics-issues-after-while-installing-ubuntu-16-04-16-10-with-nvidia-graphics/>
