> **Data Preprocessing**
>
    import csv

    file = open('lotto.csv','r')
    data = csv.reader(file)
    h = next(data)
    h2 = next(data)
    h3 = next(data)

    lotto_number = [list(map(int,row[-7:])) for row in data]

<br>

> **Topic** 

- 여태까지 가장 많이 나온 숫자?
- 7개의 당첨 번호(보너스 번호 포함)에서 짝수와 홀수의 비율은?
- 1-9,10-19,20-29,30-39,40~45 이 다섯 구간 중 가장 많이 나온 구간은?
- 자동과 수동 두 가지 중 당첨 확률이 더 높은 것은?

<br>
