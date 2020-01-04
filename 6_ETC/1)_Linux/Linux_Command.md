## Linux Command

### 1. Head

```
head -n 4 example.sql
```
<img width="708" alt="1" src="https://user-images.githubusercontent.com/26552500/71760115-5c76b400-2e86-11ea-9e31-91195eaf17a6.png">

```linux
cat example.sql | head -n 3
```
<img width="718" alt="2" src="https://user-images.githubusercontent.com/26552500/71760121-6c8e9380-2e86-11ea-9316-ebc453f7f8d6.png">


## 2. Tail

``````
cat example.sql |tail -n 5
``````
<img width="602" alt="3" src="https://user-images.githubusercontent.com/26552500/71760124-7e703680-2e86-11ea-81bf-61b492032581.png">

### -f : 업데이트 되는 내용을 보여줌

<img width="857" alt="4" src="https://user-images.githubusercontent.com/26552500/71760125-7e703680-2e86-11ea-8509-06d6626ac890.png">

##### hihi 가 추가되면 tail 끝에 추가되는 것이 보임

##### Log 파일에 저장되는 로그를 실시간으로 확인 가능함

<img width="852" alt="5" src="https://user-images.githubusercontent.com/26552500/71760126-7e703680-2e86-11ea-8b2b-bc656629e411.png">

## 3. WC

Line / Word / Bite 출력
``````
wc example.sql 
``````
<img width="510" alt="1-3-1" src="https://user-images.githubusercontent.com/26552500/71760140-a790c700-2e86-11ea-90d6-347a382707fa.png">


head와 같이 사용
``````
head -n 5 example.sql | wc 
``````
<img width="700" alt="1-3-2" src="https://user-images.githubusercontent.com/26552500/71760141-a8295d80-2e86-11ea-9fd8-612ec4e0648f.png">


Line 만 출력
``````
head -n 5 example.sql | wc -l 
``````
<img width="657" alt="1-3-3" src="https://user-images.githubusercontent.com/26552500/71760142-a8295d80-2e86-11ea-8568-2133b6b6d080.png">

``````
cat example.sql | wc -l
``````
<img width="626" alt="1-3-4" src="https://user-images.githubusercontent.com/26552500/71760143-a8295d80-2e86-11ea-8050-97c3ed4b065d.png">


파일 내용 앞에 줄 수 표시
``````
nl example.sql 
``````
<img width="721" alt="1-3-5" src="https://user-images.githubusercontent.com/26552500/71760144-a8295d80-2e86-11ea-8de0-d4a67c0d61be.png">


파일 바이트 확인 (5934)
``````
ls -al
``````
<img width="586" alt="1-3-6" src="https://user-images.githubusercontent.com/26552500/71760145-a8295d80-2e86-11ea-8ff0-08f9732864df.png">


두개의 파일 비교 및 합산
``````
wc example_1.sql example_2.sql
``````
<img width="695" alt="1-3-7" src="https://user-images.githubusercontent.com/26552500/71760146-a8295d80-2e86-11ea-9042-be74c63872c5.png">


전체 파일 비교 및 합산
``````
wc *.sql
``````
<img width="471" alt="1-3-8" src="https://user-images.githubusercontent.com/26552500/71760147-a8c1f400-2e86-11ea-9d06-8a454d20e7f0.png">


라인 수만 출력 / 파일이름 제거
``````
wc example_1.sql |awk '{print $1}'
``````
<img width="700" alt="1-3-9" src="https://user-images.githubusercontent.com/26552500/71760148-a8c1f400-2e86-11ea-9e77-9390d58588c4.png">
