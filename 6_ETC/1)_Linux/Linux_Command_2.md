# Linux_Command_2 [NL, SORT, UNIQ, CUT]

## 1. NL

줄라인 표시

``````
nl example_1.sql
``````
<img width="838" alt="Screen Shot 2020-01-04 at 11 04 00 PM" src="https://user-images.githubusercontent.com/26552500/71775279-50edc080-2f4c-11ea-876f-1dcf24085a25.png">


``````
cat example_1.sql | nl
``````
<img width="837" alt="Screen Shot 2020-01-04 at 11 05 06 PM" src="https://user-images.githubusercontent.com/26552500/71775280-51865700-2f4c-11ea-80a8-5399b15915b2.png">


WC 명령문은 라인 총 숫자나타내며, NL은 각 라인별 숫자확인

``````
wc -l example_1.sql 
nl example_1.sql | tail
``````
<img width="670" alt="Screen Shot 2020-01-04 at 11 38 43 PM" src="https://user-images.githubusercontent.com/26552500/71775283-724eac80-2f4c-11ea-9037-37706ae22fef.png">


만약에  NL이 공백을 숫자로 포함안시킬때는 옵션 -ba 를 준다

``````
nl -ba example_1.sql |tail
``````
<img width="832" alt="Screen Shot 2020-01-04 at 11 13 46 PM" src="https://user-images.githubusercontent.com/26552500/71775284-724eac80-2f4c-11ea-8006-f0d53bd9a9b8.png">


## 2. SORT

앞글자 순서대로 정렬

``````
cat example_1.sql | sort
``````
<img width="670" alt="Screen Shot 2020-01-04 at 11 38 43 PM" src="https://user-images.githubusercontent.com/26552500/71775339-3b2ccb00-2f4d-11ea-9c7c-df39014c2233.png">

Delimiter is ':' and 3번째 컬럼을 숫자로 변환 후 sort
``````
cat example_1.sql | sort -t: -k 3 -n --debug
``````

Delimiter is ':' and 3번째 컬럼 and then 1번째 컬럼을 숫자로 변환 후 sort
``````
cat example_1.sql | sort -t: -k 3,3 -k 1,1 -n --debug
``````

파일 사이즈별 정렬

``````
ls -al | sort -k 5 -n
``````
<img width="807" alt="Screen Shot 2020-01-05 at 6 33 09 PM" src="https://user-images.githubusercontent.com/26552500/71791196-0d558e00-3002-11ea-86ae-c5c77652d47a.png">


## 3. Uniq

연속으로 중복된 것 제거

``````
uniq aa | nl
``````
<img width="545" alt="Screen Shot 2020-01-05 at 8 51 37 PM" src="https://user-images.githubusercontent.com/26552500/71791205-18a8b980-3002-11ea-9a39-4814a38fc17d.png">



정렬후 연속으로 중복된 것 제거 (명령어 순서 중요)

``````
sort aa | uniq | nl
``````
<img width="615" alt="Screen Shot 2020-01-05 at 8 53 51 PM" src="https://user-images.githubusercontent.com/26552500/71791215-25c5a880-3002-11ea-916b-cd971e6928ec.png">

추가로 대소문자 제거 ( sort -f 옵션 : 대소문자 무시, uniq -i : 대소문자 무시)

``````
sort aa -f | uniq -i | nl
``````
<img width="669" alt="Screen Shot 2020-01-05 at 8 57 11 PM" src="https://user-images.githubusercontent.com/26552500/71791227-31b16a80-3002-11ea-8f88-5a202db3cf5b.png">


파일 생성 월만 표시

``````
ls -al | sort -k 6 | awk '{print $6}' 
ls -al | sort -k 6 | awk '{print $6}' | uniq
``````
<img width="869" alt="Screen Shot 2020-01-05 at 9 20 01 PM" src="https://user-images.githubusercontent.com/26552500/71791234-38d87880-3002-11ea-8e2a-774fb4a48219.png">

## 4. CUT

공백을 기준으로 첫번째 컬럼을 나눔

``````
head hosts | cut -d ' ' -f1
``````
<img width="729" alt="Screen Shot 2020-01-06 at 7 30 39 PM" src="https://user-images.githubusercontent.com/26552500/71861418-f1aebe00-30bb-11ea-917d-5d360f113a33.png">


1 - 10 바이트만 출력

``````
ls -al | head| cut -b -10
``````
<img width="837" alt="Screen Shot 2020-01-06 at 7 33 38 PM" src="https://user-images.githubusercontent.com/26552500/71861650-a943d000-30bc-11ea-9ee2-ebb34be475f9.png">


