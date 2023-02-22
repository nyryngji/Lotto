# Lotto number prediction project

> **Why?**

- 실생활에 적용할 수 있는 것, 바로 결과를 낼 수 있는 것 이 두 가지를 모두 충족시키는 것이라 생각되었기에 
- (사실 나의 사심 채우기가 더 강하다. 로또 번호 알아내려는 이유가 뭐 거창한 게 있나.)

<br>

> **How?** 

- 로또 1등 당첨을 기준으로 데이터 분석을 실행해나갈 예정 
- 데이터 분석의 결과를 토대로 직접 로또 구매 및 결과 공유 예정 
<br>

> **Data source**

- [동행복권](https://www.dhlottery.co.kr/common.do?method=main)
<br>

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

> **Result**

- 로또 구매 금액보다 당첨 금액이 더 많도록 즉, 손해 보지 않는 것이 목표이다.
