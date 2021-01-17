# 7. 터미널로 배우는 리눅스 운영체제   
   
## 7-20 문제 1   
test.csv에서 남성과 여성이 몇 명인지 세어봅시다. 우선 tail 을 통해 첫 줄을 제외한 나머지 줄을 출력하고, cut으로 성별이 들어있는 열만 추출한 다음, ④로 뭔가 쓱싹 한 다음에 uniq로 각각 세어봅시다.   
```
june@juneoh-ubuntu:~$ tail -n ① titanic.csv | cut -d② -f③ | ④ | uniq ⑤ 
314 female
577 male
```
### 정답:   
```
tail -n+2 test.csv | cut -d"," -f5 | sort | uniq -c
```
   
## 7-20 문제 2   
test.csv에서 성이 Brown인 사람이 몇 명인지 세어봅시다. 성이 아닌 나머지 이름에 Brown이 들어가는 경우도 있으니 조심해야 합니다.   
```
june@juneoh-ubuntu:~$ cat titanic.csv | grep '①' | wc ②
4
```
### 정답:   
```
cat test.csv | grep 'Brown' | wc -l
``` 