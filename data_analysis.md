> **Data Preprocessing**
>
    import csv

    file = open('lotto.csv','r')
    data = csv.reader(file)
    h = next(data)
    h2 = next(data)
    h3 = next(data)

    lotto_number = [list(map(int,row[-7:])) for row in data] # 역대 당첨 번호 
    last_10 = lotto_number[:10] # 최근 10회차 번호

<br>

> **Topic** 

- 최근 10회차 번호 내에서 분석, 단 최근 10회차 나온 번호에서 3연속 나온 번호는 제외 
>
    lotto_num = []
    for i in last_10:
        for j in i:
            lotto_num.append(j)

    x = [i for i in lotto_num if lotto_num.count(i)<=2]
    print(set(sorted(x)))
<br>

- 1,2,8,9,6,7,13,14,29,30,36,37,34,35,41,42 하나 이상 포함 시켜라 

- 3연속 숫자는 피해라 ex) 43,44,45

- 로또 예상 번호 사이트 이용하기 -> 3연속 번호는 확률이 높다 

- 패턴이 좌우 대칭 되는 번호를 노려라

- 로또 번호 당첨 횟수, 날짜 끝숫자를 넣어라

- 홀수와 짝수의 비율 구하기

<br>
