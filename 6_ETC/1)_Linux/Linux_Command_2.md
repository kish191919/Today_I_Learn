# Linux_Command_2 

## 1. NL

줄라인 표시

``````
nl example_1.sql
``````



``````
cat example_1.sql | nl
``````



WC 명령문은 라인 총 숫자나타내며, NL은 각 라인별 숫자확인

``````
wc -l example_1.sql 
nl example_1.sql | tail
``````



만약에  NL이 공백을 숫자로 포함안시킬때는 옵션 -ba 를 준다

``````
nl -ba example_1.sql |tail
``````



## 2. SORT

앞글자 순서대로 정렬

``````
cat example_1.sql | sort
``````

