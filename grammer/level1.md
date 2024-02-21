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

## 유클리드 호제를 활용한 최대공약수 / 최소 공배수
```java
//최대 공약수
static int gbc(int a, int b) {
  //유클리드 호제는 a>b인 상황에서만 가능하다.
  //따라서 a<b인 경우 a와 b를 바꾸어줘야한다.
  if (a < b) {
    int tmp = a;
    a = b;
    b = tmp;
  }
  while(b != 0) {
    int r = a%b;
    a = b;
    b = r;
  }
  return a;
}

//최소 공배수 -> 최대 공약수 공식을 활용하여 계산한다.
static int lcm(int a, int b) {
  return a*b / gbc(a, b);
}
```

## 문자열에 숫자만 있는지 판별하기
```java
import java.util.regex.Pattern; //정적 임포트
String pattern = "\\d+"; //숫자를 의미
Pattern.matches(pattern, str) //bool 리턴
```

## 이중배열의 생성
```java
int[][] param // 주어질때
int[][] arr = new int[param.length][param[0].length];
```

## 이중 배열의 반복문
```java
for (int i=0; i<arr.length; i++) {
	for (int j=0; j<arr[i].length; j++) {
	}
}
```

## steam().map
```java
stream.mapToInt(i->i).toArray();
stream.mapToLong(i->i).toArray();
stream.mapToDouble(i->i).toArray();
```
