# Problem 8/30

## Quiz : "Dictionaries and Maps"
입력받은 데이터를 딕셔너리 데이터 타입으로 변환하고, 딕셔너리 타입의 데이터를 검색하는 문제

## Task
   = 연락처 데이터를 만들고 이름을 검색하여 결과를 출력한다.
   - 연락처의 데이터 수를 결정하는 정수 n 을 입력받는다.
   - n 개의 "name=phoneNumber" 를 입력받아 딕셔너리 형태로 변환한다.
   - 검색할 이름을 입력받는다.
   - 연락처에서 입력한 이름을 검색하여, 이름이 존재하면 다음과 같이 출력한다.
      - "name=phoneNumber"
   - 이름이 존재하지 않으면 다음과 같이 출력한다.
      - "Not found"

## Input Format
   - 연락처의 인원수에 해당하는 정수 n을 입력받는다.
   - 이름과 8자리의 전화번호를 입력받는다.
      - sam 11223344
   - 검색할 이름을 입력받는다.

## Ountput Format
   - 검색한 이름이 연락처에 있으면 다음과 같이 출력한다.
      - sam=11223344
   - 검색한 이름이 연락처에 없으면 다음과 같이 출력한다. 
      - Not found

## Constraints
   - 1 <= n <= 100000
   - i <= queries <= 100000

## Explanation
   - n=3 (key, value)
   - phoneBook = {(sam, 99887766), (tom, 11223344), (hong, 33445566)}

## Solution !!
1. final code :

   1) 연락처의 전체 갯수를 정하는 n 입력 받기.
   ```
   n = int(input())
   ```
   2) 이름과 8자리의 데이터를 입력 받고 dict 타입으로 변환하기.
   ```
   ### 데이터를 n 번 입력받을 때마다 .split()을 사용하여 공백을 기준으로 데이터를 구분해준다.
   ### key 와 value 로 저장하기 위해 리스트 컴프리핸션을 사용하여 k와 v 변수로 나눠준다.

   phoneBook = dict((k,v) for k,v in [input().split() for i in range(n)])
   ```
   3) 검색할 데이터를 입력받는다. 
      - 코드 테스트에서 10,000 의 연락처 데이터를 생성하고 10,000 개의 이름을 검색하는데 이떄에 EOFerror 가 발생한다. 
      - EOFerror 는 갑자기 입력변수가 중단될 때 생기는 오류라고 한다. 
      - 이 에러를 해결하려면 try, exception 함수를 설정해 주어야 한다.
   ```
   while True :
      try:
   	 find_name = input().stirp()
	 if find_name in phoneBook :
	     print("{}={}".format(find_name, phoneBook[find_name])
	 else :
	     print("Not found")
      except :
          break
   ```
   4) code
   ```
   n = int(input())
   phoneBook = dict((k,v) for k,v in [input().split() for i in range(n)])
   
   while True :
        try :
	     find_name = input().stirp()
	          if find_name in phoneBook :
	               print("{}={}".format(find_name, phoneBook[find_name])
	          else :
	               print("Not found")
	except :
	     break
   ```


