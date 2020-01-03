## Linux Command

### 1. Head

```
head -n 4 example.sql
```

![image-20200102212333115](/Users/s107166/Library/Application Support/typora-user-images/image-20200102212333115.png)



```linux
cat example.sql | head -n 3
```

![1](/Users/s107166/Desktop/1.png)



## 2. Tail

``````
cat example.sql |tail -n 5
``````

![image-20200102213804016](/Users/s107166/Library/Application Support/typora-user-images/image-20200102213804016.png)



### -f : 업데이트 되는 내용을 보여줌

![image-20200102214441922](/Users/s107166/Library/Application Support/typora-user-images/image-20200102214441922.png)

##### hihi 가 추가되면 tail 끝에 추가되는 것이 보임

##### Log 파일에 저장되는 로그를 실시간으로 확인 가능함

![image-20200102214601925](/Users/s107166/Library/Application Support/typora-user-images/image-20200102214601925.png)