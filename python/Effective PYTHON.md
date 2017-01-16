# 파이썬 코딩의 기술

#### 1. 사용 중인 파이썬의 버전을 알자.
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

#### 2. PEP8스타일 가이드를 따르자.
파이썬 개선 제안서(Python Enhancement Proposal) #8
PEP8은 파이썬 코드를 어떻게 구성할지 알려주는 스타일 가이드이다.
