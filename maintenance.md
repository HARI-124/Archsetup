## Updating and Synchronising the packages

Packages can be synced with `pacman -Syu`command

To get the latest mirros use `reflector --country COUNTRY --latest 5 --sort rate --save /etc/pacman.d/mirrorlist` command to       
get the best top 5 mirrors. This requires reflector package. If you encounter any issue while downloading stuff or during synchronising just run
the reflector command the mirrorlist will be refreshed and the error will be solved if it was based on tyhe mirrorlist.

for example I got an error for ssl certificate failed for that particular mirror so after running the reflector the error vanished.

