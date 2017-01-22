# java Collections

## 구조
```
  Collections
    Set : 중복 불가
      HashSet
      TreeSet
    List : 중복 허용
      ArrayList
      LinkedList : doubly circular linked list
      Stack : 수시계산, 수식괄호검사, 워드의 undo/redo
      Queue : 최근사용문서, 인쇄작업 대기목록, 버퍼(buffer)
  Map : key, value 형태
    HashMap : 검색에 관한한 성능이 좋다.
    TreeMap : 범위검색이나 정렬이 필요한 경우 사용
```
+ ArrayList : 배열기반, 데이터의 추가와 삭제에 불리, 순차적인 추가삭제는 제일 빠름. 임의의 요소에 대한 접근성이 뛰어남
+ LinkedList : 연결기반, 데이터의 추가와 삭제에 유리. 임의의 요소에 대한 접근성이 좋지 않다.
+ HashMap : 배열과 연결이 결합된 형태. 추가, 삭제, 검색, 접근성이 모두 뛰어남. 검색에는 최고성능 보인다.
+ TreeMap : 연결기반, 정렬과 검색(특히 범위검색)에 적합. 검색성능은 HashMap보다 떨어짐
+ Stack : Vector를 상속받아 구현
+ Queue : LinkedList가 Queue인터페이스를 구현
+ Properties : Hashtable을 상속받아 구현
+ HashSet : HashMap을 이용해서 구현
+ TreeSet : TreeMap을 이용해서 구현
+ LinkedHashMap, LinkedHashSet : HashMap과 HashSet에 저장순성유지기능을 추가하였음.
