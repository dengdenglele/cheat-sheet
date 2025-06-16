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

