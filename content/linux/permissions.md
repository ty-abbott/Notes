## Permissions with linux

- To CD into a directory the executable permission must be set to it. That was the problem with the website - at somepoint the execute permission was changed for the directory that hosts the code.
- So sites-enabled could not figure out where the root folder was because it did not have access to it. 


### SUDO
- running a command with sudo without needing to input a password is possible through visudo
- it is important to get the spacing right between the sections
