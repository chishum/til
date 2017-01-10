# python의 collection 파악

## 리스트
임의의 객체들의 순서열이다.
가변이다. (append, insert 가능)
```
  names = ["Dave", "Mark", "Ann", "Phil"]
  names = [1, "Dave", 3.14, ["Mark", 7, 8, [100, 101]], 10]
  names = []
  names = list()

  fvalues = [float(line) for line in lines]
```
## 튜플
리스트와 유사하다.
불변이다.
```
  stock = ('GOOG', 100, 490.10)
  stock = 'GOOG', 100, 490.10
  address = ('www.python.org', 80)
  person = (first_name, last_name, phone)

  a = ()
  b = (item,)
  c = item,

  name, shares, price = stock
  host, port = address
  first_name, last_name, phone = person

   for name, shares, price in portfolio:
    total += shares * price

```

## 집합
집합(set)은 객체들의 순서 없는 모음을 담는 데 사용한다.
중복이 없다.
```
  s = set([3, 5, 9, 10])
  t = set("Hello") // 이 경우 'H','e','l','o'만 담긴다.
```

## 사전
사전(disctionary)은 키로 색인되는 객체들을 담는 연관 배열 혹은 해시 테이블이다.
주로 문자열이 키로서 사용되지만, 숫자나 튜플 같은 객체도 키로 사용될 수 있다.
리스트나 사전 같이 가변객체는 키로 사용할 수 없다.
```
  stock = {
    "name" : "GOOG",
    "shares" : 100,
    "price" : 490.10
  }
  name = stock["name"]

  prices = {}
  prices = disc()

  #키 목록 얻기
  k = list(prices)

```
