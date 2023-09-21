# Table of Contents
- [For Beginner](./RESOURCES.md#for-beginner)

## Recommend
Recommend use this script general for boss.
```
?foe = boss & foe.distance <= 10 &
^item.GetCooldown("bardiche") <= 0 |
^item.GetCooldown("bardiche") > 870
  equip bardiche
  activate R
```

## For Beginner
### Wood ☆4~5
- Require
  - resources - tar (potion)
  - Dashing Shield
- Recommend
  - Sword Damage 10 ↑
```
?loc = deadwood
  brew tar

  ?loc.stars = 4
    ?hp < 6
      activate potion
  :?loc.stars = 5
    ?hp < 8
      activate potion

  ?foe.distance < 22
    ?foe = mosquito
      equipL ouroboros
      equipR crossbow *7
    :?foe = scarab
      equipL sword *8
      equipR dashing shield
    :?foe = boss
      ?foe.distance > 10
        equipL triskelion
        equipR dashing shield
      :
        equipL sword *8
        equipR crossbow *7
  :
    ?harvest.distance < 10
        equipL ouroboros
        equipR hatchet
      ?harvest.distance <= 4
        equipL moon
        equipR hatchet
        ?item.GetCooldown(“hatchet”) <= 0 & item.CanActivate()
          activate R
    :?pickup.distance < 10
        equipL ouroboros
        equipL star
    :
        equipL triskelion
        equipR star
```
### Tar ☆4
- Require
  - Crossbow ☆7 ↑
- Recommend
  - resources - wood (potion)
```
?loc = caves
  brew wood

  ?foe.distance < 22
    activate potion

  ?pickup.distance < 10
    equipL star

  ?foe = boss
    equipL shield *7
    equipR crossbow *7
  :?foe.distance < 22
    equipL ouroboros
    equipR crossbow *7
  :
    ?pickup.distance < 10
      equipL star
      equipR triskelion
    :
      equipL ouroboros
      equipR triskelion
```
