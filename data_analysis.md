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

> **algorithm** 

**1.** 최근 10회차 번호 내에서 분석, 단 최근 10회차 나온 번호에서 3연속 나온 번호는 제외 
>
    lotto_num = []
    for i in last_10:
        for j in i:
            lotto_num.append(j)

    x = [i for i in lotto_num if lotto_num.count(i)<=2]
    print(set(sorted(x)))
<br>

**2.** [1,2,8,9,6,7,13,14,29,30,36,37,34,35,41,42] 중 하나 포함시키라는 규칙에 따라 2번과 교집합을 찾았음
>
    cond = [1,2,8,9,6,7,13,14,29,30,36,37,34,35,41,42]
    x = list(nums.intersection(cond)) # 2번과 cond 중 중복되는 숫자 리스트 

**3.** 제일 최근 로또 번호를 소거

- 연속으로 두 번 나올 확률이 매우 적음
<br>

**4.** 최근 10회 로또 번호 분포로 숫자 범위 정하기 -> 보통 4개 분야    
> 
    import matplotlib.pyplot as plt 
    n0109 = [] # 0~9까지 
    n1019 = [] # 10~19까지 
    n2029 = [] # 20~29까지 
    n3039 = [] # 30~39까지 
    n4045 = [] # 40~45까지 

    for i in lotto_num:
        if 1<=i<=9:
            n0109.append(i)
        elif 10<=i<=19:
            n1019.append(i)
        elif 20<=i<=29:
            n2029.append(i)
        elif 30<=i<=39:
            n3039.append(i)
        else:
            n4045.append(i)

    ratio = [len(n0109)/70,len(n1019)/70,len(n2029)/70,len(n3039)/70,len(n4045)/70]
    label = ['1~9','10~19','20~29','30~39','40~45']

    plt.rc('font',family='Malgun Gothic')
    plt.rcParams['axes.unicode_minus']=False

    plt.title('최근 10회 로또 번호 분포')
    plt.pie(ratio, labels=label,autopct='%.1f%%')
    plt.show()

**5.** 로또 번호 당첨 횟수, 날짜 끝숫자를 넣기

- 1057회 -> 7
<br>

**6.** 홀수와 짝수의 비율 구하기(보너스 숫자 제외 6개의 숫자 기준)
>
    percent = []

    for i[:-1] in last_10:
        even = 0
        for j in i:
            if j%2==0:
                even += 1
        percent.append(even)

    print(percent)
    
<br>

**7.** 소거 후 남은 숫자 중 더 높은 확률의 번호 고르기 
>
    x = []
    for i in lotto_number:
        for j in i:
            x.append(j)

    lotto_number = x
    print(lotto_number.count(28)/len(x)*100)
 
