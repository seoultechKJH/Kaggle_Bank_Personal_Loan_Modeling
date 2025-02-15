# Kaggle_Bank_Personal_Loan_Modeling
Stable DT, Stable CRI, Random Forest 알고리즘을 사용하여 Kaggle의 은행 개인대출 데이터 분석 및 대출 경향이 높은 고객 특성 도출

- 테크니컬 포트폴리오 기술평가항목 : 1, 7, 8


# Dataset
- 총 데이터 수 : 5000개
- 분석목적 : 대출사업 확장을 위한 잠재 대출상품 구매 고객 선별 모델 수립


# variable
- ID : 고객 ID
- Age : 고객 나이
- Experience : 경력 연차수
- Income : 고객의 연소득 ($000)
- ZIPCode : 우편번호
- Family : 가족구성원 수
- CCAvg : 월평균 신용카드 지출 ($000)
- Education : 학력(1 - 학사, 2 - 석박사, 3 - 전문직)
- Mortgage : 주택담보대출 가치 (있는 경우) ($000)
- Securities Account : 고객의 유가증권계정 개설 여부
- CD Account : 고객의 양도성예금증서(CD) 계좌 개설 여부
- Online : 고객의 온라인 뱅킹 사용 여부
- CreditCard : 고객의 Universal Bank 신용카드 사용 여부

- Personal Loan : 지난 캠페인에서의 개인 대출 제안 수락 여부


# Result
- Relative frequency histogram을 보았을 때, 고객 연소득이 많을수록 개인 대출을 많이 이용함
- 연소득이 많음에도 불구하고 개인 대출을 많이 이용하는 원인에 대하여 직관적으로 추측해 보았을 때, 투자활동에서 ‘레버리지 전략’을 사용하기 위해 대출을 이용하는 가능성이 있을 것으로 추측함(레버리지 전략 : 자기자본금에 대출금을 더하여 투자함으로써, 실제 투자한 자기자본금 대비 수익률을 극대화시키는 전략)
- 또한 월평균 신용카드 지출 수준이 중간 범위인 사람들, 학력이 높은 사람들이 대출을 많이 이용하는 경향이 있음
- Stable DT 결과로부터 추출한 Rule에 따르면 '중위권 소득의 고객이면서, 적절한 소비를 하는 성향을 갖고 있으며, 대학원급 이상의 지식을 갖고 있으며, 가족 수가 적은 고객이 대출을 이용한다는 사실을 추측할 수 있음
- Stable DT의 결과에서 정밀도는 의미가 불분명하지만, 높은 재현율을 보이므로 해당 결과로부터 추출한 Rule이 개인대출 고객을 선별하기 위한 특징이라는 사실은 파악할 수 있음 (정밀도는 영업 범위를 극대화시켜 이윤을 창출하는 것과 관련있고, 재현율은 특정 고객 집단의 특성을 파악하는 것과 관련있음)
- Random Forest 결과가 좋게 나왔으며, 이를 통해 추출한 Feature Importance를 통해 고객의 소득, 월평균 지출, 지식수준이 핵심적인 공략 요소라는 것을 파악할 수 있음

# < Stable DT 결과 >
![image](https://github.com/user-attachments/assets/ac75e776-dc0a-4125-b941-86369d0122ab)

![image](https://github.com/user-attachments/assets/ff903266-c499-4291-9c5f-88ad0b1039b8)

![image](https://github.com/user-attachments/assets/867746f5-995c-4eae-94ad-fd0e460e19bb)

# < Stable CRI 결과 >
![image](https://github.com/user-attachments/assets/5ce70d00-e212-4214-91d8-a6fca37c5599)

# < Random Forest 결과 >
![image](https://github.com/user-attachments/assets/3089b6f8-81d0-4ba1-b531-ef959a2d76d6)
