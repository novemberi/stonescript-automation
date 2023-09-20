# Caves ☆ 4
Require ☆7 crossbow
Potion **wood**
```
?loc = caves
  ?foe.distance < 22 & item.potion ! empty & item.potion = auto
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
