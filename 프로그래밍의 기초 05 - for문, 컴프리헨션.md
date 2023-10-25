## 반복문 - For문

- For문 
  - iterable한 객체, 반복 가능한 객체를 더이상 꺼낼 수 없을 때까지 반복함
  - 리스트, 튜플, 셋, 딕셔너리, 문자열 등 객체들에 모두 적용 가능함
    ```python
    # 전체 lst출력하기
    lst = [3, 33, 100, 23, 81, 44]
    for i in lst :
      print(i)
    
    # 3의 배수만 추출하기
    for i in lst :
      if n%3 == 0 :
        print(n)

    # 앞문자만 대문자로 변경 출력
    lst = ['dog', 'cat', 'rabbit']
    for i in lst :
      print(s[0].upper() + s[1:])
    #결과 : Dog Cat Rabbit
    ```
    
- Range함수 
  - For문이랑 함께 아주 자주 사용됨
  - 슬라이싱 기법을 이용해서 특정 구간의 숫자 범위를 만들어 주는 함수 
    ```python
    # 2~10까지 숫자중(11미만) 2씩 건너뛴 숫자를 리스트화
    list(range(2,11,2))
    # 결과 : [2, 4, 6, 8, 10]

    # 1~40까지 숫자중 4의 배수만 출력
    for x in range(4, 41, 4) :
      print(x)

    # 4~40까지 숫자중 뒤에서부터 거꾸로 4의 배수만 출력
    for x in range(40, 3, -4) :
      print(x)
    ```
- 중첩 for문 
  - 구구단 만들기
    ```python
    for i in range(2, 10) :
      for j in range(1,10) :
        print(f" {i} x {j} = {i*j}")
    ```

  - 별찍기 : range에 변수 넣기
    - 언더바로 처리하는 이유는, 함수 내에서 추후에 또 사용하지 않을 변수이기 때문
    ```python
    n = 5
    for i in range(n) : #0~4
      for _ in range(i+1): #range 1, 2, 3, 4, 5
        print("*", end="")
      print() 
    ```
  - 별찍기 :  반대 방향
    - print함수는 자동으로 줄바꿈이됨. 기본값이 \n으로 지정되어 있기 때문. end =""로 줄바꿈을 없앨 수 있음
    - print()로 줄바꿈 직접 설정
    ```python
    for i in range(1, 6) :
      for _ in range(5-i) : #공백 출력
        print(" ", end = "")
      for _ in range(i) :
        print("*", end = "")
      print() #줄바꿈을 직접 설정해주기 
    ```
## For문 관련 함수 

- enumerate 함수 
  - iterable한 객체를 꺼낼 때, 인덱스도 같이 꺼낼 수 있는 객체를 생성해준다. 
  - for문에서는 index를 같이 뽑아야 할 때가 많아 활용도 매우 높은 중요한 함수!
  - enumerate 함수의 결과는 그 자체로 print out되지 않음. list로 변환해 확인 가능함
    - ex. <enumerate at 0x105e44c40> 식으로 객체로 반환됨 
    - list(enumerate(score_list))
  - 따라서 추출할 때 unpacking 개념 활용, 'for index, score  in score_list' 식으로 꺼내서 확인해야
    ```python
    for index, score in enumerate(score_list):
      print(f"{index} 번째 점수는 {score}입니다.")
    ```
