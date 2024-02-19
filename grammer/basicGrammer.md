# Grammer

## stream
```java
//int 배열의 경우
//검사해야할것이 있다면 == if문 사용이 필요시 -> filter사용
//오름차순 정렬을 해야한다면 sorted 사용
int[] result = Arrays.stream(arr).filter().sorted().toArray();

//배열에서 max/min
Arrays.stream(arr).max().getAsInt();
Arrays.stream(arr).min().getAsInt();
```

## 리스트 초기화
* `Arrays.asList()`로 리스트를 초기화 할경우 `static` 리스트가 만들어져서 수정 삭제시 에러가 발생한다.
* 따라서 `new ArrayList<>(Arrays.asList(val1, val2...))` 로 초기화 하는것이 좋다.

## 정수 리스트 값 삭제
* 정수 list가 존재할때 이 리스트에서 특정 값을 삭제할경우에는 `arr.remove()`가 아니라
* `arr.remove(Integer.valueOf(num))`을 사용해야한다.

## collectors 사용시 주의
* `import java.util.*;`만으로는 Collectors를 사용할 수 없다.
* `import java.util.stream.Collectors;`로 정적 임포트를 해주어야한다.

## int 배열을 list로 변환
```java
import java.util.*;
import java.util.stream.Collectors;
List<Integer> sortedList = Arrays.stream(arr).boxed().collect(Collectors.toList());
```

## boxed() -> primitive 타입을 래퍼 클래스로 박싱
* boxed는 primitive 타입을 해당하는 래퍼 클래스로 박싱하는데 사용된다.
* 배열을 list로 변경시 래퍼 타입을 사용하므로 boxed() 함수를 사용해야한다.

## 배열 정렬
* 배열은 `Arrays.sort()`를 사용하여 정렬하나, 이는 정렬이 순차적으로 실행된다.
* `Arrays.parallelSort()`를 사용하면 병렬적으로 정렬할 수 있다.

## 리스트를 배열로 변환
* 원하는 타입을 사용하여 toArray안에 생성자 참조를 이용하면 된다.
```java
list.toArray(type[]::new); 
```

## 입력
* 한 줄씩 입력받는경우 BufferedReader를 쓰는것이 좋다.
```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String input = br.readLine();
```
* 한줄에 입력받는경우, 띄어쓰기로 구분할때에는 StringTokenizer를 쓰는것이 좋다. split보다 빠름
```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in());  //10 20 30
StringTokenizer st = new StringTokenizer(br.readLine());
int a = Integer.parseInt(st.nextToken()); //10
int b = Integer.parseInt(st.nextToken()); //20
int c = Integer.parseInt(st.nextToken()); //30
```

## 출력
* System.out.println 보다 BufferedWriter가 더욱 빠르다
* write, newLine, flush가 한 사이클로 이루어진다고 보면된다.
* write는 char, String만 받기 때문에 숫자를 사용할경우 String.valueOf()로 감싸라
```java
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
bw.write("hello bf!");  //쓰고
bw.newLine();  //줄바꾸고
bw.flush();  //실제 출력
bw.close();
```

## 문자열
```java
length() //반드시()를 붙인다.
isEmpty()
charAt(index)  //index를 매개변수로
indexOf(str)  //str의 index를 반환
substring(num1, num2) //num1이상, num2미만으로 자름
replace(char1, char2) //char1을 char2로 변경
equals()
compareTo(str)  //str보다 앞이면 -1, 같으면 0, 뒤면 1
contains(str)  //str이 포함되는지
```

## StringBuilder
```java
StringBuilder sb = new StringBuilder();
sb.append(str)
sb.reverse()
sb.toString() //항상 마지막엔 String으로 형변환
```

## 리스트
* List를 의미한다, Collections는 list만 가능하다.
```java
add(val)
add(index, val)
addAll(list) //list를 더한다
remove(index or val)
clear()
isEmpty()
size()
contains(val)
Collections.max(list)
Collections.min(list)
Collections.sort(list)  //오름
Collections.sort(list, Collections.reverseOrder())  //내림
Collections.reverse(list)  //뒤집기

/*
반드시 오름차순 정렬 후 검색
찾으면 위치가 반환된다. 찾지못하면 insert-1의 값이 리턴된다.
*/
Collections.binarySearch(list, val)
```

## 배열과 list
* Arrays.메서드()는 배열과 list 모두 사용가능
```java
//array -> list
Arrays.asList(array)  //이렇게 하면 list가 변경 불가능하다.
new ArrayList<>(Arrays.asList(array)) //이렇게 하면 변경 가능하다

//list -> array
타입[] 이름 = list.toArray(new 타입[list.size()]);

//int array -> Integer list
//int는 Integer로
int[] arr = {0, 1,2,3};
List<Integer> list = new ArrayList<>(Arrays.asList(arr));

//Integer list -> int array
List<Integer> list = new ArrayList<>();
int[] arr = list.stream().mapToInt(x -> x).toArray();

//배열에서 max/min
Arrays.stream(arr).max().getAsInt();
Arrays.stream(arr).min().getAsInt();
```

## stack
```java
Stack<타입> 이름 = new Stack<>();
push(val)
pop() //꺼내기 + 제거
size()
empty()
contains(val)
peek() //최상단 요소 꺼내기
clear()
```

## hash set
* 중복허용 x, 순서 x
```java
HashSet<타입> 이름 = new HashSet<>();
add(val)
remove(val)
contains(val)
clear()
//출력시
for(타입 val : 이름) {
    sout(val)
}
```

## 해쉬맵
* 중복허용, 순서 x
```java
HashMap<키타입, 밸류타입> 이름 = new HashMap<>();
put(key, val)
remove(key)
containsKey(key)
containsValue(val)
clear()

//key val 출력
for (키타입 key : 이름.keySet()) {
    sout("val" : 이름.get(key));
}
```

## 큐
```java
Queue<Integer> q = new LinkedList<>();
q.add(val);  //삽입, 꽉찰경우 예외발생
q.offer(val);  //삽입, 꽉찰경우 false리턴

q.peek(); //루트 반환

q.remove();  //삭제 및 반환, 큐가 비어있으면 예외발생
q.poll();  //삭제 및 반환 큐가 비어있으면 null반환

q.clear();
q.isEmpty();
```

## 우선순위큐
```java
PriorityQueue<Integer> pq = PriorityQueue<Integer>(); // 최소힙
PriorityQeueu<Integer> pq = PriorityQueue<Integer>(Collections.reverseOrder()); // 최대힙
pq.add(val);
pq.peek();  //root 반환
pq.remove();
```
