# clustering_student
학생들의 클래스에 따른 학습 방법, 시험 난이도, 시험 점수 등으로 clustering 분석

Data : 중학교 1학년 2019~2021 271명에 대한 정보가 들어있는 560,164개의 데이터

Scaling : MinMaxScaler

Type : A(추가학습), C(맞춤학습), P(만점학습), R(정규학습), S(셀프테스트), X(오답클리닉)
Hard(난이도) : 3, 6, 9, 12, 15(숫자가 작을수록 어려움, 높을수록 쉬움)

feature 
 1. Type별 시험지를 얼마나 풀어봤는지(시험응시횟수)
 2. Hard별 문제의 정답률
 3. 전체 정답률
 4. Type별 문제에 따른 평균 정답률

총 14개 세부 feature로 PCA 진행, 누적기여율을 통해 적절한 PCA 값을 찾고 Elbow method을 통해 클러스터링을 위한 적당한 k 값을 찾음
클러스터링이 어느 정도 잘 나왔다고 판단하고 XGB를 통해 feature별로 어느정도 영향을 끼치는지 확인
