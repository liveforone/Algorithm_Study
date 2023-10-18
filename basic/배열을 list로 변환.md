# 배열을 리스트로 변환
* List를 toArray 메서드에 파라메터로 넘어가는 배열 객체의 size만큼의 배열로 전환한다.
* 단, 해당 List size가 인자로 넘어가는 배열 객체의 size보다 클때, 해당 List의 size로 배열이 만들어진다.
* 반대로 해당 List size가 인자로 넘어가는 배열객체의 size보다 작을때는, 인자로 넘어가는 배열객체의 size로 배열이 만들어진다.
* 결론 : 인자로 넘어가는 배열의 사이즈가 0이라서 원래 배열의 크기만큼 생성된다.
```java
import java.util.*;
String[] answer = new String[str.length];
answer = stringList.toArray(new String[0]);
```
