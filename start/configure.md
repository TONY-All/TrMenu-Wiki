---
description: Configure the TrMenu
---

# Configure

## Plugin Files

| File / Dir | Description |
| :--- | :--- |
| settings.yml | Plugin's settings |
| lang/en\_US.yml | Language file |
| menus | Menu folder |

## Configurations

{% code title="settings.yml" %}
```yaml
# TrMenu Wiki: https://trmenu.trixey.cn

# Do not change
CONFIG-VERSION: 0

# Locale loading priority
# Put your locale in the first
# Contributing Translations: https://trmenu.trixey.cn/other/locale
LOCALE-PRIORITY:
  - en_US
  - zh_CN
  - zh_TW
  - vi_VN

# Options
OPTIONS:
  # Enable this, the plugin will not display the logo when loading
  SILENT: false
  # Similar material matches
  MATERIAL-SIMILAR-DEGREE: 0.8
  # Anti inventory click spam (millisecs)
  ANTI-CLICK-SPAM: 200
  # Should enable the menu file listener?
  MENU-FILE-LISTENER:
    ENABLE: true
    NOTIFY: true

# Custom loading files as menus
MENU-FILES: []

# Create menus inside the settings file
MENUS:
  - internalMenu:
      title: 'Internal Menu in settings.yml'
      shape:
        - '#########'
        - '    |    '
        - '#########'
      buttons:
        '#':
          display:
            mats: green stained glass pane
        '|':
          display:
            mats: apple
            name: '&6Nice to meet you~'

```
{% endcode %}

## Locale

{% code title="en\_US.yml" %}
```yaml
PLUGIN:
  LOADING:
    - ''
    - '&3Tr&bMenu &7loading...'
    - ''
  ENABLED: '&8[&3Tr&bMenu&8] &bINFO &8| &3Loaded. TrMenu &av{0} &3has been enabled.'
  DISABLED: '&8[&3Tr&bMenu&8] &bINFO &8| &7Disabled. Thanks for using :)'
  DEPEND:
    DOWNLOAD: '&8[&3Tr&bMenu&8] &eDEPEND &8| &7Downloading depend plugin &f{0} &7...'
    INSTALL: '&8[&3Tr&bMenu&8] &eDEPEND &8| &7Successfullly downloaded &3{0} &7, restarting the server...'
    INSTALL-FAILED: '&8[&3Tr&bMenu&8] &eDEPEND &8| &7Failed to install depend plugin &c{0} &7...'
  HOOKED: '&8[&3Tr&bMenu&8] &eDEPEND &8| &7Hooked &6{0}&7...'
  UPDATE-NOTIFY:
    LATEST: '&8[&3Tr&bMenu&8] &2You''re running the latest version of &3TrMenu&a.'
    DEV: '&8[&3Tr&bMenu&8] &6You''re running the development version of &3TrMenu&6.'
    TOO-OLD:
      - "&8--------------------------------------------------"
      - "&r"
      - "&8# &4The version of &cTrMenu &4you are running is too old"
      - "&8# &4Please update to the latest version in time!"
      - "&8# &r"
      - "&8# &4SpigotMC: &chttps://www.spigotmc.org/resources/74284"
      - "&8# &r"
      - "&8# &r"
      - "&8# &4The server will start in &c&l{0} secs &4..."
      - "&r"
      - "&8--------------------------------------------------"
    HEADER:
      - ''
      - '§3--------------------------------------------------'
      - '&7▪ &3TrMenu &aUpdate Notify &8{0} &7➦ &8{1}'
    FOOTER:
      - '&7▪ &2Github: &a&nhttps://github.com/Arasple/TrMenu/releases/latest'
      - '§3--------------------------------------------------'

ERROR:
  HDB: '&8[&3Tr&bMenu&8] &cERROR &8| &cYou can not use &6{0} &csince there''s no &6HeadDatabase&c.'
  VERSION: '&8[&3Tr&bMenu&8] &cERROR &8| &7Plugin version error. Please re-download the plugin.'
  JS:
    - '&8[&3Tr&bMenu&8] &cERROR &8| &cExpression error: &2{0}'
    - '&6{1}'
    - '&8{2}'

MENU:
  LOADED-AUTOLY: '&8[&3Tr&bMenu&8] &bINFO &8| &7File changes, automatically reloaded menu &f{0}&7...'
  LOADED-SUCCESS: '&8[&3Tr&bMenu&8] &bINFO &8| &7Loaded &a{0} &7menus... &8[&7{1} Ms&8]'
  LOADED-FAILURE: '&8[&3Tr&bMenu&8] &6WARN &8| &7There''re &6{0} &7menus failed to load. Please check these errors...'
  DEPEND-EXPANSIONS-REQUIRED: '&8[&3Tr&bMenu&8] &7You need to install PlaceholderAPI expansions &6{0} &7to use that menu.'
  NOT-EXIST: '&8[&3Tr&bMenu&8] &7Menu doesn''t exist...'
  NOT-ENOUGH-ARGS: '&8[&3Tr&bMenu&8] &7Requires &6{0} &7arguments.'
  LOADING-ERRORS:
    NO-SHAPE: '&7Menu &6{0} &7''s shape is invalid &2{1}'
    NO-BUTTONS: '&7Menu &6{0} &7do not contain Buttons section'
    YAML: '&7Menu &6{0} &7has YAML error &c{1} &8{2}'
    CONFLICT-OPEN-COMMANDS: '&7Menu &6{0} &7has conflicting open command with menu &6{1}...'
    CONFLICT-OPEN-ITEMS: '&7Menu &6{0} &7has conflicting bind item lore with menu &6{1}...'
    ICON-NO-CONDITION: '&7Menu &6{0} &7button &3{1} &7has empty condition for priority icon'
    ICON-LOAD-FAILED: '&7Menu &6{0} &7button &3{1} &7failed to load. &3{2}&8{3}'

COMMANDS:
  NOT-PLAYER: '&8[&3Tr&bMenu&8] &cPlayer only...'
  NO-PLAYER: '&8[&3Tr&bMenu&8] &cPlayer is not online...'
  OPENED-FOR: '&8[&3Tr&bMenu&8] &3Opened the menu for the player...'
  LIST:
    - '&8--------------------------------------------------'
    - '&3Tr&bMenu &7- Menu List'
    - ''
  LIST-FORMAT:
    - '&8▫ &6{0}'
  HELP-PAGE:
    ==: JSON
    text:
      - '&8--------------------------------------------------'
      - '&3Tr&bMenu &7- Advanced Dynamic Menu &6*{0}'
      - ''
      - '&8▪ <&7/&3{1} List@list> &8— &7 List menus'
      - '&8▪ <&7/&3{1} Reload@reload> &8— &7 Reload all menus'
      - '&8▪ <&7/&3{1} Open [Menu] [Id]@open> &8— &7 Open a menu for a player'
      - '&8▪ <&7/&3{1} About@about> &8- &7 About plugin'
      - ''
      - '&8--------------------------------------------------'
    args:
      list:
        hover: |-
          &7Click to execute
        command: '/trmenu list'
      reload:
        hover: |-
          &7Click to execute
        command: '/trmenu reload'
      open:
        hover: |-
          &7Click to execute
        suggest: '/trmenu open'
      about:
        hover: |-
          &7Click to view
        suggest: '/trmenu about'
```
{% endcode %}



