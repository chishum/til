# 해싱과 해시함수
해싱이란 해싱함수(hash function)을 이용해서 데이터를 해시테이블(hash table)에 저장하고 검색하는 기법을 말한다. 해시함수는 데이터가 저장되어 있는 곳을 알려 주기 때문에 다량의 데이터 중에서도 원하는 데이터를 빠르게 찾을 수 있다.
해싱을 구현한 컬렉션 클래스로는 HashSet, HashMap, Hashtable 등이 있다. Hashtable은 컬렉션 프레임웍이 도입되면서 HashMap으로 대체되었으나 이전 소스와의 호환성 문제로 남겨 두고 있다. 가능하면 Hashtable대신 Hashmap을 사용하도록 하자.

해싱에서 사용하는 자료구조는 배열과 링크드 리스트의 조합을 되어 있다.
저장할 데이터의 키를 해시함수에 넣으면 배열의 한 요소를 얻게 되고, 다시 그 곳에 연결되어 있는 링크드 리스트에 저장하게 된다.