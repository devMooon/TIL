# **1. 제목**

## 예시
```
# h1
## h2
### h3
#### h4
##### h5
###### h6

수평선
***
```

## 결과
># h1        
>## h2
>### h3
>#### h4
>##### h5
>###### h6
>수평선
>***


<br><br><br>


# **2. 줄바꿈**
## 예시
```
안녕<br>하세요.
```

## 결과
>안녕<br>하세요.


<br><br><br>


# **3. 목록**
## 예시
```
1. 순서 있는 목록
3. 순서를 잘못써도 순서대로 입력됨(3->2)

- 순서 없는 목록 1
    - 목록 1.1
        - 목록 1.2
- 순서 없는 목록 2

        한 칸 띄고 Tab 두번
```

## 결과
>1. 순서 있는 목록
>3. 순서를 잘못써도 순서대로 입력됨(3->2)
>
>- 순서 없는 목록 1
>    - 목록 1.1
>        - 목록 1.2
>- 순서 없는 목록 2
>
>        한 칸 띄고 Tab 두번


<br><br><br>


# **4. 폰트**
## 예시
```
*italic*
**bold**
***bold & italic***
~cancel~
<u>under line</u>
```

## 결과
>*italic* <br>
>**bold** <br>
>***bold & italic*** <br>
> ~~cancel~~ <br>
><u>under line</u>


<br><br><br>


# **5. 인용문**
## 예시
```
>안녕하세요
>>지금은 오후 8시 25분입니다.
>>>시간이 빨리가네요..ㅎ
```

## 결과
>안녕하세요
>>지금은 오후 8시 25분입니다.
>>>시간이 빨리가네요..ㅎ


<br><br><br>


# **6. 인용문**
## 예시
```
>안녕하세요
>>지금은 오후 8시 25분입니다.
>>>시간이 빨리가네요..ㅎ
```

## 결과
>안녕하세요
>>지금은 오후 8시 25분입니다.
>>>시간이 빨리가네요..ㅎ


<br><br><br>


# **7. 코드 작성**
## 예시
```
    ```
    hello world
    ```
```
```
    ```python
    print("Hello world")
    ```
```
```
    ```c
    printf("Hello world, %d", 1);
    int i = 0
    ```
```
```
    ```java
    system.out.println("Hello world");
    int i = 0
    var k = 5
    ```
```

## 결과
 ```
    hello world
```
```python
    print("Hello world")
```
```c
    printf("Hello world, %d", 1);
    int i = 0
```
```java
    system.out.println("Hello world");
    int i = 0
    var k = 5
```


<br><br><br>


# **8. 링크**
## 예시
```
[인라인 링크](https://github.com/devMooon)
url링크 <https://github.com/devMooon>
![이미지 설명](이미지 링크)
```

## 결과
>[인라인 링크](https://github.com/devMooon) <br>
>url링크 <https://github.com/devMooon><br>
![디즈니공주](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile29.uf.tistory.com%2Fimage%2F99D428505EDB76B8067656)


<br><br><br>


# **9. 테이블**
## 예시
```
| 제목1 | 제목2 | 제목3 |
|:----------|:----------:|----------:|
| 왼쪽정렬 | 가운데정렬 | 오른쪽정렬 |
| 본문1 | 본문2 | 본문3 |
```

## 결과
>| 제목1 | 제목2 | 제목3 |
>|:----------|:----------:|----------:|
>| 왼쪽정렬 | 가운데정렬 | 오른쪽정렬 |
>| 본문1 | 본문2 | 본문3 |


<br><br><br>


# **10. 체크박스**
## 예시
```
- [ ] 운영체제 강의 듣기
- [x] 자바 예제 공부하기
```

## 결과
>- [ ] 운영체제 강의 듣기
>- [x] 자바 예제 공부하기