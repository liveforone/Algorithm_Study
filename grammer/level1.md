# 레벨1

## 인수 분해 : 약수 구하기
```java
for (int i=1; i<=n; i++) {
  if (n % i == 0) {
    //이때 i는 약수이다.
  }
}
```

## 문자에서 숫자 추출
* charAt() 등을 사용해서 문자열에서 문자를 추출한 경우에 사용하면 좋다.
```java
Character.getNumericValue(char)
```

## 문자열 대소문자 무시하고 비교
```java
equalsIgnoreCase() 
```

## 제곱근 찾기
* 제곱근을 찾을때 단순히 `Math.sqrt()`를 쓰는것에서 그치지 말고 이 값이 정수인지 판별해야한다.
* 만약 sqrt 한 값을 1로 나누었을때 0보다 크면 정수가 아니다.
* 이유는 모든 정수는 1로 나누어 떨어지기 때문이다.
```java
double num = Math.sqrt(n);
if ( num % 1 > 0 ) {
  //정수 아님
}
```

## steam().map
```java
stream.mapToInt(i->i).toArray();
stream.mapToLong(i->i).toArray();
stream.mapToDouble(i->i).toArray();
```
