# ZYNC
*Zync* is for rsync what fstab is for mounting. Simply define all files and
directories that you want to sync between two computers in a config file and call
*zync* to either push or pull theses files. The point of this script is that
it makes it easier to switch computers i.e. when doing home office. The zync.conf
ensures that all files of all different hosts can be organized in one place.

## Install
```
install -Dpm 755 ./zync /usr/local/bin/zync
```

## Usage
```
Usage: zync [-c ./other-zync.conf] cmd

  -c file     path to the config file to read. Default: ~/.config/zync.conf

CMDS:
  push alias
  pull alias
    either push or pull from the alias specified in the zync.conf
  list
    list all aliases specified in the zync.conf

-------------------------------------------------------------------------------

CONFIG FORMAT:

  [alias name]
  [[config]]
  user remote-user
  host ip/domain
  key ~/.ssh/your-public-key.pub
  [[files]]
  # TYPE      PATH HERE       PATH THERE        IGNORE
  d|f         /path           ~/other/path      fileA,dirB/
  ...

  [other alias name]
  [[config]]
  ...
.....
```
