# **숙제 2문제**

**이번 주에 배운 여러 기법을 바탕으로 이전에 봤던 MNIST 데이터셋을 이용하여 딥러닝 구조를 PyTorch로 짜는 문제입니다 :)**



### **Q1-1) 아래에 주어진 주석을 기반으로 하여 코딩을 해주세요.**

- 모두의 딥러닝 시즌2 github 코드에 힌트가 있습니다 :) https://github.com/deeplearningzerotoall/PyTorch 



```python
import torch
import torchvision.datasets as dsets
import torchvision.transforms as transforms
import matplotlib.pylab as plt
import random


# 파라미터 설정 (learning rate, training epochs, batch_size)
learning_rate = 0.1
training_epochs = 15
batch_size = 100


#train과 test set으로 나누어 MNIST data 불러오기

'Fill this blank!


#dataset loader에 train과 test할당하기(batch size, shuffle, drop_last 잘 설정할 것!)

'Fill this blank!


# Layer 쌓기 (조건: 3개의 Layer 사용, DropOut 사용 (p=0.3), ReLU 함수 사용, Batch normalization하기)
# 각 Layer의 Hidden node 수 : 1st Layer (784,100), 2nd Layer(100,100),3rd Layer(100,10)

'Fill this blank!'


#xavier initialization을 이용하여 각 layer의 weight 초기화

'Fill this blank!'



# torch.nn.Sequential을 이용하여 model 정의하기(쌓는 순서: linear-Batch Normalization Layer - ReLU- DropOut)

'Fill this blank!'



# Loss Function 정의하기 (CrossEntropy를 사용할 것!)

'Fill this blank!'




#optimizer 정의하기 (Adam optimizer를 사용할 것!)

'Fill this blank!'




#cost 계산을 위한 변수 설정
train_total_batch = len(train_loader)




#Training epoch (cost 값 초기 설정(0으로)과 model의 train 설정 꼭 할 것) 
for epoch in range(training_epochs):
	
	'Fill this blank!'   

    
#train dataset을 불러오고(X,Y 불러오기), back propagation과 optimizer를 사용하여 loss를 최적화하는 코드
    for X, Y in train_loader:
       
    	'Fill this blank!'
    
	 	avg_cost += bn_loss / train_total_batch
        
        
    print('Epoch:', '%04d' % (epoch + 1), 'cost =', '{:.9f}'.format(avg_cost))

print('Learning finished')



#test data로 모델의 정확도를 검증하는 코드 (model의 evaluation mode 설정 꼭 할 것)
#X_test 불러올 때 view를 사용하여 차원 변환할 것/ Y_test를 불러올때 labels사용
#accuracy의 초기 값 설정(0으로) 꼭 할 것

with torch.no_grad():
   
	'Fill this blank!'





    
    print("Accuracy: ", bn_acc.item())
    
    
    
    ##Test set에서 random으로 data를 뽑아 Label과 Prediction을 비교하는 코드 
    r = random.randint(0, len(mnist_test)-1)
    X_single_data = mnist_test.test_data[r:r + 1].view(-1, 28 *28).float()
    Y_single_data = mnist_test.test_labels[r:r + 1]
    
    print('Label: ', Y_single_data.item())
    single_prediction = bn_model(X_single_data)
    print('Prediction: ', torch.argmax(single_prediction, 1).item())
    


```





### **Q1-2) 지금까지는 Layer의 수를 바꾸거나, Batch Normalization Layer를 추가하는 등 Layer에만 변화를 주며 모델의 성능을 향상 시켰습니다. **

**이번 문제에서는 위에서 만든 모델에서 있던 Layer 들의 Hidden node 수를 증가 또는 감소 (ex: 200, 300, 50...) 시켰을 때, <u>train set에서의 cost</u>와 <u>test set에서 Accuracy</u>가 기존 결과와 비교하였을 때 어떻게 달라졌는지 비교해주시면 됩니다.**



- **Hidden node 수 변화 시 주의해야 할 점 **

  

  - 각 Layer의 앞 뒤 node 숫자 일치시키기

  - Batch Normalizaion Layer의 node 숫자와 일치시키기

    

```python
linear1 = torch.nn.Linear(784, 100, bias=True)
linear2 = torch.nn.Linear(100, 100, bias=True)
linear3 = torch.nn.Linear(100, 10, bias=True)


bn1 = torch.nn.BatchNorm1d(100)
bn2 = torch.nn.BatchNorm1d(100)

```



```python
linear1 = torch.nn.Linear(784, 200, bias=True)
linear2 = torch.nn.Linear(200, 150, bias=True)
linear3 = torch.nn.Linear(150, 10, bias=True)


bn1 = torch.nn.BatchNorm1d(200)
bn2 = torch.nn.BatchNorm1d(150)
```



