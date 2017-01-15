# 독특한 파이썬 문법

## 튜플 활용 
```
  teamstandings = [('SK',38,25, 0), ('KIA',39,29,0)]
  for ts in teamstandings :
    team, win, lost, draw = ts
    games = win + lost + draw
    winrate = float(win) / (win + lost)
    format = '%s 팀은 총 %d 경기 중 % 승으로 승률은 %.3f입니다.'
    print(format % (team, games, win, winrate))
```

## lambda 활용 
```
  import os, random
  
  dir = 'scripts/py4fun/' if os.getcwd().find('sl4a') > 0 else ''
  txt = open(dir + 'wordlist.txt').read()
  words = filter(lambda x: len(x) > 0 and not x.startswith('#'), txt.splitlines())
  
  while True:
    print(random.choice(words))
    raw_input()
```
  
## 한 줄 표현 
```
 mdb = set(line.strip() for line in open('Million Dollat Baby.txt'))
 list([cast for cast in all if cast.startwith('Morgan')])
```
