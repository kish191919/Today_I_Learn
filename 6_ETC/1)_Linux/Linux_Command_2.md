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
<img width="834" alt="Screen Shot 2020-01-04 at 11 08 33 PM" src="https://user-images.githubusercontent.com/26552500/71775285-724eac80-2f4c-11ea-8bbe-bf8d57567aa5.png">

Delimiter is ':' and 3번째 컬럼을 숫자로 변환 후 sort
``````
cat example_1.sql | sort -t: -k 3 -n --debug
``````

Delimiter is ':' and 3번째 컬럼 and then 1번째 컬럼을 숫자로 변환 후 sort
``````
cat example_1.sql | sort -t: -k 3,3 -k 1,1 -n --debug
``````