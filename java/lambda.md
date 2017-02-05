# java8의 새로 추가된 lambda 함수 분석

*java collection에 대해서 먼저 파악하자*

### 파악할 내용
#### Consumer
#### Method Reference
#### Anonymous Inner Class

### java.util.function 패키지
|함수형 인터페이스|메서드|설명|
|---|---|---|
|java.lang.Runnable|void run()|매개변수도 없고, 반환값도 없음.|
|Supplier< T >|T get()|매개변수는 없고, 반환값만 있음|
|Consumer< T >|void accept(T t)|Supplier와 반대로 매개변수만 있고, 반환값이 없음|
|Function< T,R >|R apply(T t)|일반적인 함수. 하나의 매개변수를 받아서 결과를 반환|
|Predicate< T >|boolean test(T t)|조건식을 표현하는 데 사용됨. 매개변수는 하나. 반환 타입은 boolean|
|BiConsumer< T,U >|void accept(T t, U u)|두 개의 매개변수만 있고, 반환값이 없음|
|BiPredicate< T,U >|boolean test(T t, U u)|조건식을 표현하는 데 사용됨. 매개변수는 둘, 반환값은 boolean|
|BiFunction< T,U,R >|R apply(T t, U u)|두 개의 매개변수를 받아서 하나의 결과를 반환|
