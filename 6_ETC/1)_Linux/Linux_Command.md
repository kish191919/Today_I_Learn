## Linux Command

### 1. Head

```
head -n 4 example.sql
```

![1](/Users/s107166/Desktop/GITHUB/Today_I_Learn/6_ETC/Screen_Shot/1.png)

```linux
cat example.sql | head -n 3
```

![2](/Users/s107166/Desktop/GITHUB/Today_I_Learn/6_ETC/Screen_Shot/2.png)



## 2. Tail

``````
cat example.sql |tail -n 5
``````

![3](/Users/s107166/Desktop/GITHUB/Today_I_Learn/6_ETC/Screen_Shot/3.png)

### -f : 업데이트 되는 내용을 보여줌

![4](/Users/s107166/Desktop/GITHUB/Today_I_Learn/6_ETC/Screen_Shot/4.png)

##### hihi 가 추가되면 tail 끝에 추가되는 것이 보임

##### Log 파일에 저장되는 로그를 실시간으로 확인 가능함

![5](/Users/s107166/Desktop/GITHUB/Today_I_Learn/6_ETC/Screen_Shot/5.png)