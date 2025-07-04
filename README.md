# cheat-sheet

## ansible-playbook
```bash
- name: Print something
  debug:
    msg: "Something: {{ something }}"

- name: Run a role from anywhere
  include_role:
    name: just_another_role
```

## apt
```
apt rdepends <package-name>
apt-policy cache <package-name>
```

## apt-key (deprecated!!!)
```
apt-key list # show all keys
gpg --no-default-keyring --keyring /etc/apt/trusted.gpg --list-keys # view contents inside of trusted.gpg file
sudo apt-key del <key-id> # if key is only in /etc/apt/trusted.gpg and does not have a key file
ls /etc/apt/trusted.gpg.d/ # view files inside of trusted.gpg.d/ directory
sudo rm /etc/apt/trusted.gpg.d/<key-file>.gpg # delete a single key file
sudo apt update # make sure apt recognizes new/deleted/modified keys
```

## chmod
```
cd /path/to/directory/with/incorrect/permissions # assuming everything is green, equals 777 permissions
find . -type f -exec chmod 644 {} \; # Make all regular files 644
find . -type d -exec chmod 755 {} \; # Make all directories 755
chmod 755 gradlew # Make specific scripts executable
```

## dd
```
time dd if=/dev/zero of=datei bs=1M count=10240 # how long it takes to write 10 GB
time dd if=datei of=/dev/null # how long it takes to read
dd if=/dev/zero of=/path/of/largefile.bin bs=1G count=400 # write a 400 GB big special file with null bytes
```

## decoding
```
echo "decode-this-passphrase" | base64 --decode # do not copy the highlighted % sign at the end of the line
```

## diagnostics
```
sudo smartctl -a /dev/sdX
```

## git
```bash
git checkout -- .
git commit --allow-empty -m "creates a new commmit, even if there are no changes in the repository"
git fetch --prune # check, if remote branches still exist. If not, then remove information about origin locally
git log --oneline
```

## gpg
```
gpg list-keys
```

## grep
```
grep root /etc/passwd
grep -r docker /etc/apt
```

## hardware/system clock
```
date
sudo hwclock --show
sudo hwclock --systohc # set hardware clock to system time
sudo hwclock --hctosys # set system time to hardware clock
```

## journalctl
```bash
journalctl -xe # -x additional eXplanation when available, -e jump to End of journal logs
journalctl -xeu <name-of-a>.service # -u filter log entries by a specific systemd Unit
```

## log stuff
```bash
view /var/log/syslog
dmesg
```

## mount stuff
```bash
sudo apt install lvm2 # might be missing, gparted told me to install it
sudo lvscan # check if active
sudo lvchange -ay /dev/vgubuntu/root # activate if inactive
sudo mkdir -p /mnt/vgubuntu-root # create mount point
sudo mount /dev/vgubuntu/root /mnt/vgubuntu-root # mount
df -h # verify
sudo umount /mnt/vgubuntu-root # unmount
```

## R
```
rm(list = ls())
```

## swap
```
cat /proc/sys/vm/swappiness # read current swappiness, Debian/Ubuntu default 60, servers 1
echo "vm.swappiness = 1" | sudo tee /etc/sysctl.d/vm.swappiness.conf # set swappiness then reboot
```

## systemctl
```
systemctl # list all active services
systemctl reboot --firmware-setup # enter BIOS via systemd
```

## vim
```
:set nocp?
```

## /etc/sudoers.d/drop-in-file-no-extension
```
sudo visudo /etc/sudoers.d/drop-in-file-no-extension
username ALL=(ALL) NOPASSWD: /usr/bin/apt update, /usr/bin/apt upgrade -y
```
