# Shop

## Simple sell and buy

```yaml
Title: 'Buy & Sell'

Shape:
  - ''
  - '    A'
  - ''

Open-Commands:
  - 'sellapple'
  - 'buyapple'

Options:
  Depend-Expansions:
    - 'vault'
    - 'checkitem'

Buttons:
  'A':
    update: 20
    display:
      mats: 'apple'
      lore:
        - - ''
          - '&f· &7Buy: &e100$'
          - '&f· &7Sell: &220$'
          - ''
          - '&3LeftClick to buy &8| &6RightClick to sell'
          - ''
    actions:
      all: ['sound: BLOCK_NOTE_BLOCK_PLING-1-2']
      left:
        - 'Close'
        - 'Tell: &cYou don''t have enough money_||_Break:<Requirement: %vault_eco_balance% < 100>'
        - 'Console: eco take %player_name% 100'
        - 'Console: give %player_name% apple 1'
        - 'Title: <title=&3&lSuccess><subtitle=&8[&a&l+&8] &c&lAPPLE &7* &61>'
      right:
        - 'Close'
        - 'Tell: &cYou don''t have apples to sell_||_Break:<Requirement: "%checkitem_mat:APPLE,amt:1%" == "no">'
        - 'Console: eco give %player_name% 20'
        - 'Console: clear %player_name% apple 1'

```

{% hint style="info" %}
_**\_\|\|\_**_ is used to compound multiple actions in one line, and their options\(like requirement\) are shared
{% endhint %}

