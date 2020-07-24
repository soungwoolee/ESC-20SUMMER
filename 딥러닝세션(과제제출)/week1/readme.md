## 과제 가이드라인
Jupyter에서 코드 및 마크다운문법으로 과제 완료하신 후에 깃헙에 'Week1 HW1_Regression_서경덕.ipynb'으로 업로드 해주시면 됩니다.

## 첫주차 과제

#### 첫주차 세션자료 살짝 수정하여 깃헙에 업로드했습니다(레퍼런스, 이미지 소스 안붙은것 추가하고 순서 살짝 바꿨습니다.)
#### 과제는 7월30일(목) 세션전까지 하시면 됩니다. 당일 랜덤으로 한 명 발표예정입니다!

과제 4문제
이번 숙제는 많은 시간을 요하지 않는 문제로 구성했습니다. 첫 두 문제는 앞에 낸 문제와 똑같은 것입니다.
제가 참조한 https://sumniya.tistory.com/26 에서 아래 문제에 대한 지식을 얻을 수도 있겠습니다.

Q1) 이 경우에서는 Type 1 error가 높을까요? Type 2 Error가 높을까요? FP, FN과 관련지어 설명해주세요

Q2-1) Accuracy, Precision and Recall이 무엇인지 TP,FP,FN,TN의 식으로 나타내 주세요.

Q2-2) Precision and Recall에 관한 제가 든 예시가 아닌 실생활 예시 하나를 들어주세요. 제가 생각이 나는 예시 분야는 "양치기 소년 우화", "암 수술" 등등이 있습니다. 생각하신 예시에서 성공확률의 threshold를 높인다는 것은 무슨 의미인가요? 생각하신 예시에서는 그 threshold를 늘리는 것이 비교적 합리적일까요? 아니면 비합리적일까요? 혹은 알 수 없을까요?

가령 양치기 소년 예시에서는 "늑대다!" 할 때, 계속 일어나는데 늑대가 없어서 잠을 설치는 것과 계속 무시했는데 실제로 늑대가 와서 다 잡아먹히는 사건을 비교할 수 있을 거에요.
각자의 의견을 근거를 들어 적어주시기 바랍니다.

Q3) 코드 따라해보고 주석 달기!

(제가 만든 문제가 아닙니다. source : https://www.geeksforgeeks.org/identifying-handwritten-digits-using-logistic-regression-pytorch/)

MNIST라는 Dataset을 들어보셨는지 모르겠습니다. 딥러닝을 배울 때 많이 쓰이죠. 손글씨 숫자 데이터인데요, 그 숫자가 무엇인지 기계학습을 통해 예측하도록 합시다!

데이터에 대한 설명 : https://sdc-james.gitbook.io/onebook/4.-and/5.1./5.1.3.-mnist-dataset

Q3 코드 출처 : https://www.geeksforgeeks.org/identifying-handwritten-digits-using-logistic-regression-pytorch/

Q4-1) 2-4 코드에서 optim.SGD를 사용하지않고 코드를 짠다면 어떤 방식으로 짜야할까요? 설명해주세요.

Q4-2) Gradient descent 코드를 구현하는 문제입니다. 2-4의 코드에서 다른 optimizer(3개 ex)adam, rmsprop, sgd에 momentum 추가 등등)를 이용하여 결과값을 비교해주세요.
