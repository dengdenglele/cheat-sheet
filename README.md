# cheat-sheet

## git
```bash
git checkout -- .
git commit --allow-empty -m "creates a new commmit, even if there are no changes in the repository"
git fetch --prune
git log --oneline
```

## grep
```
grep root /etc/passwd
grep -r docker /etc/apt
```

## mount stuff
```bash
sudo lvscan # check if active
sudo lvchange -ay /dev/vgubuntu/root # activate if inactive
sudo mkdir -p /mnt/vgubuntu-root # create mount point
sudo mount /dev/vgubuntu/root /mnt/vgubuntu-root # mount
df -h # verify
sudo umount /mnt/vgubuntu-root # unmount
```

## ansible-playbook
```bash
- name: Print something
  debug:
    msg: "Something: {{ something }}"

- name: Run a role from anywhere
  include_role:
    name: just_another_role
```

## log stuff
```bash
view /var/log/syslog
dmesg
```
## decoding
```
echo "decode-this-passphrase" | base64 --decode # do not copy the highlighted % sign at the end of the line
```
