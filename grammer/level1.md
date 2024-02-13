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
