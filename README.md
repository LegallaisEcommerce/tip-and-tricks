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
