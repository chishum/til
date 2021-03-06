# 파이썬 코딩의 기술

### 1. 사용 중인 파이썬의 버전을 알자.
+ 파이썬의 주요 버전인 파이썬 2, 파이썬 3 모두 여전히 활발히 사용된다.
+ 새 파이썬 프로젝트를 시작할 때는 파이썬 3를 사용하는 편이 좋다.

```shell
$ python --version
```
```python
import sys
print(sys.version_info)
print(sys.version)

>>>
sys.version_info(major=3, minor=4, micro=2, releaselevel='final', serial=0)
```

### 2. PEP8스타일 가이드를 따르자.
+ 파이썬 개선 제안서(Python Enhancement Proposal) #8
+ PEP8은 파이썬 코드를 어떻게 구성할지 알려주는 스타일 가이드이다.

#### 화이트스페이스
+ 탭이 아닌 스페이스로 들여쓴다.
+ 문법적으로 의미 있는 들여쓰기는 각 수준마다 스페이스 네 개를 사용한다.
+ 한 줄의 문자 길이가 79자 이하여야 한다.
+ 표현식이 길어서 다음 줄로 이어지면 일반적인 들여쓰기 수준에 추가로 스페이스 네 개를 사용한다.
+ 파일에서 함수와 클래스는 빈 줄 두 개로 구분해야 한다.
+ 클래스에서 메서드는 빈 줄 하나로 구분해야 한다.
+ 리스트 인덱스, 함수 호출, 키워드 인수 할당에는 스페이스를 사용하지 않는다.
+ 변수 할당 앞뒤에 스페이스를 하나만 사용한다.

#### 명명
+ 함수, 변수, 속성은 lowercase_underscore 형식을 따른다.
+ 보호(protected) 인스턴스 속성은 _leading_underscore 형식을 따른다.
+ 비공개(private) 인스턴스 속성은 __double_leading_underscore 형식을 따른다.
+ 클래스와 예외는 CapitalizeWord 형식을 따른다.
+ 모듈 수준 상수는 ALL_CAPS 형식을 따른다.
+ 클래스의 인스턴스 메서도에서는 첫 번째 파라미터(해당 객체를 참조)의 이름을 self로 지정한다.
+ 클래스 메서드에서는 첫 번째 파라미터(해당 클래스를 참조)의 이름을 cls로 지정한다.

#### 표현식과 문장
+ 긍정 표현식의 부정(if not a is b) 대신에 인라인 부정(if a is not b)을 사용한다.
+ 길이를 확인(if len(somelist) == 0)하여 빈 값([] 또는 '')을 확인하지 않는다. if not somelist를 사용하고, 빈 값은 암시적으로 False가 된다고 가정한다.
+ 비어 있지 않은 값([1] 또는 'hi')에도 위와 같은 방식이 적용된다. 값이 비어 있지 않으면 if somelist문이 암시적으로 True가 된다.
+ 한 줄로 된 if문, for와 while 루프, except복합문을 쓰지 않는다. 이런 문장은 여러 줄로 나눠서 명료하게 작성한다.
+ 항상 파일의 맨 위에 import문을 놓는다.
+ 모듈을 임포트할 때는 항상 모듈의 절대 이름을 사용하면 현재 모듈의 경로를 기준으로 상대 경로로 된 이름을 사용하지 않는다. 예를 들어 bar 패키지의 foo 모듈을 임포트하려면 그냥 import foo가 아닌 from bar import foo라고 해야 한다.
+ 상대적인 임포트를 해야 한다면 명시적인 구문을 써서 from . import foo라고 한다.
+ 임포트는 '표준 라이브러리 모듈, 서드파티 모듈, 자신이 만든 모듈'섹션 순으로 구분해야 한다. 각각의 하위 섹션에서는 알파벳 순서로 임포트한다.

### 7. map과 filter 대신 리스트 컴프리헨션을 사용하자.
```python
a = [1,2,3,4,5,6,7,8,9,10]
squares = [x**2 for x in a]
print(squares)

map_squares = map(lambda x: x**2, a) // map

// filter
even_quqres = [x**2 for x in a if x % 2 == 0]
map_even_squares = map(lambda x: x**2, filter(lambda x: x % 2 == 0, a)) // map
assert even_squares == map_even_squares

chile_ranks = {'ghost': 1, 'habanero': 2, 'cayenne': 3}
rank_dict = {rank: name for name, rank in chile_ranks.items()}
chile_len_set = {len(name) for name in rank_dict.values()}

```

### 9.컴프리헨션이 클 때는 제너레이터 표현식을 고려하자.
+ 리스트 컴프리헨션은 큰 입력을 처리할 때 너무 많은 메모리를 소모해서 문제를 일으킬 수 있다.
+ 제너레이터 표현식은 이터레이터로 한 번에 한 출력만 만드므로 메모리 문제를 피할 수 있다.
+ 한 제너레이터 표현식에서 나온 이터레이터를 또 다른 제너레이터 표현식의 for서브표현식으로 넘기는 방식으로 제너레이터 표현식을 조합할 수 있다.
+ 제너레이터 표현식은 서로 연결되어 있을 때 매우 빠르게 실행된다.
```python
value = [int(x) for x in open('temp.txt')]
print(value)
it = (int(x) for x in open('temp.txt'))
print(it)
print(next(it))
print(next(it))
print(next(it))
print(next(it))

roots = ((x, x** 0.5) for x in it) // 위에서 4번 진행했으므로 그 이후부터 진행된다.
print(next(roots))
print(next(roots))
print(next(roots))

```

### 10. range보다는 enumerate를 사용하자.
```python
flavor_list = ['vanilla','chocolate','pecan','strawberry']
for flavor in flavor_list:
  print('%s is delicious' % flavor)

for i in range(len(flavor_list)):
  flavor = flavor_list[i]
  print('%d: %s' % (i + 1, flavor))

for i, flavor in enumerate(flavor_list):
  print('%d: %s' % (i+1, flavor))

for i, flavor in enumerate(flavor_list, 1):
  print('%d: %s' % (i, flavor))
```

### 11. 이터레이터를 병렬로 처리하려면 zip을 사용하자.
```python
names = ['Cecilia','Lise','Marie']
letters = [len(n) for n in names]

longest_name = None
max_letters = 0
for i in range(len(names)):
  count = letters[i]
  if count > max_letters:
    longest_name = names[i]
    max_letters = count
print(longest_name)
// Cecilia

for i, name in enumerate(names):
  count = letters[i]
  if count > max_letters:
    longest_name = name
    max_letters = count

for name, count in zip(names, letters):
  if count > max_letters:
    longest_name = name
    max_letters = count

```
+ python2에서는 izip을 사용해야 한다.
+ zip은 서로 length가 같을 때 사용해야 한다.
