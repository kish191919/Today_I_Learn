# Linux_Command_2 

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



## 3. Uniq

연속으로 중복된 것 제거

``````
uniq aa | nl
``````



정렬후 연속으로 중복된 것 제거 (명령어 순서 중요)

``````
sort aa | uniq | nl
``````



추가로 대소문자 제거 ( sort -f 옵션 : 대소문자 무시, uniq -i : 대소문자 무시)

``````
sort aa -f | uniq -i | nl
``````



파일 생성 월만 표시

``````
ls -al | sort -k 6 | awk '{print $6}' 
ls -al | sort -k 6 | awk '{print $6}' | uniq
``````

