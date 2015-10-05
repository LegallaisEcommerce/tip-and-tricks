#Tips and tricks

## MySQL on MacOS

### Load big dump "MySQL has gone away"

edit:
```sh
sudo vim /usr/local/mysql/my.cnf
```

add line:

```ini
max_allowed_packet = 512M
```

restart MySQL:

```sh
sudo /usr/local/mysql/support-files/mysql.server restart
```

## Numeric keyboard with iterm
To turn on the apple numeric keyboard with iterm: 

iTerm -> Preferences -> Profiles -> Keys -> Load Preset… -> xterm with numeric keypad

For zsh & the enter key type in terminal:
```sh
$ bindkey -s "^[OM" "^M"
```

## Atom preferences
config.cson

```json
"*":
  editor:
    fontSize: 14
    showInvisibles: true
    showIndentGuide: true
    autoIndentOnPaste: false
    nonWordCharacters: "./\\()\"':,.;<>~!@#%^&*|+=[]{}`?-"
    tabLength: 4
    invisibles: {}
$ bindkey -s "^[OM" "^M"
```

## Single User mode
To enter in single user mode with cmd+s method blocked. 

```
$ sudo nvram boot-args="-s"
```

Reboot 

Then to leave single user mode (carefull, you're in qwerty) :
```
$ nvram boot-args=""
```

## Repair disk
Reboot in single user mode (see above), then : 
```
$ fsck -fy
```
Wait for "The volume OS X appear to be OK" and type : 
```
$ nvram boot-args=""
$ reboot
```
## PHP Version conflict

If you update MacOs your command line PHP version doesn't match anymore your Apache PHP version. 
I order to get it fixed let's play these : 

```
$ sudo mv /usr/bin/php /usr/bin/php.old
$ sudo ln -s /usr/local/php5/bin/php /usr/bin/php
```
## Disable System Integrity Protection
On El Capitain, Apple introduced System Integrity Protection (aka "rootless").
So for instance you can't perform 
```
$ sudo mv /usr/bin/php /usr/bin/php.old
```
Thankfully you can desactivate this feature. 
Restart your mac and hold on Command+R until the Apple logo appear. 
Then go to  Utilities > Terminal.
Perform this command : 
`csrutil disable`
And restart. 
