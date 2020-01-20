---
description: 设计高级菜单需要综合运用多种动作、条件表达式
---

# 商店

## 简单的购买、出售

```yaml
  'A':
    update: 20
    display:
      mats: 'apple'
      lore:
        - - ''
          - '&f· &7售价: &e100$'
          - '&f· &7收购: &220$'
          - ''
          - '&3左键点击购买 &8| &6右键点击出售'
          - ''
    actions:
      all: ['sound: BLOCK_NOTE_BLOCK_PLING-1-2']
      left:
        - 'Close'
        - 'Tell: &c你没有足够的余额_||_Break:<Requirement: %vault_eco_balance% < 100>'
        - 'Console: eco take %player_name% 100'
        - 'Console: give %player_name% apple 1'
        - 'Title: <title=&3&l操作成功><subtitle=&a&l苹果 &cx1 &7已发放至你背包...>'
      right:
        - 'Close'
        - 'Tell: &c你没有苹果_||_Break:<Requirement: "%checkitem_mat:APPLE,amt:1%" == "no">'
        - 'Console: eco give %player_name% 20'
        - 'Console: clear %player_name% apple 1'
```



