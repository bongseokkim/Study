From Dive into Deep Learning

## Index 
+ [Multilayer Perceptrons](#multilayer-perceptrons)
+ Deep Learning Computation
+ Convolutional Neural Netwroks
+ Modern Convolutional Neural Networks
+ Recurrent Neural Networks
+ Attention Mechanisms


## Multilayer Perceptrons 

### hidden layer 
![example1](https://ko.d2l.ai/_images/singlelayer.svg)

위의 그림인 softmax regression example를 살펴보면, 모델은 affin 변환(linear transformation added by bias)을 통해 input을 직접적으로 output과 mapping한후, softmax operation을 
수행한다.
이는 다음과 같은 matrix form으로 나타낼 수 있다.
**o^=softmax(Wx+b)**
그러나 만약 레이블과 입력값이 선형적으로 연관되어 있지 않다면, 너무 강한 가정을 포함하기 떄문에 이 방법은 적절하지 않다고한다.
예를 들어 입력값이 증가하면, 다른 입력값과는 상관없이 결과값이 커지거나 작아지는 것을 의미한다.
검정색이나 희색 이미지을 이용해서 강아지나 고양이를 분류하는 케이스를 생각해보면, 각 픽셀의 값을 증가시키면 강아지라고 판별할 확률값을 높이거나 내려가는 경우를 생각해 볼수있다.
결국 이렇게 된다면 결국 강아지는 모두 검정색이고 고양이는 모두 흰색이거나 그 반대라는 것을 의미하기 때문에 이런 선형 가정은 적합하지 않다.

### Incorporating Hidden Layers
![example2](https://d2l.ai/_images/mlp.svg)

이러한 선형 모델의 한계점을 해결하고, general class of function으로 만들기 위해서 히든레이어를 추가하는 것이다.
가장 쉬운방법 중 하나는 각 층위에  fully-connected layer를 추가하는 것이다. 최종적으로 output을 만들어 낼때 까지 각각의 layer들은 그위의 layer들에 주입된다. 
이러한 구조를 multilayer perceptron 이라고 부른다.위의 MLP는 4개의 input과 3개의 output이 있으며, 5개의 hidden unit이 존재한다. 
