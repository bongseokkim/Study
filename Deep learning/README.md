From Dive into Deep Learning

## Index 
+ Multilayer Perceptrons
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
그러나 만약 레이블과 입력값이 선형적으로 연관되어 있지 않다면, 이 방법은 적절하지 않다. 너무 강한 가정을 포함하게 된다.
예를 들어 입력값이 증가하면, 다른 입력값과는 상관없이 결과값이 커지거나 작아지는 것을 의미한다.

### Incorporating Hidden Layers
![example2](https://d2l.ai/_images/mlp.svg)
이러한 선형 모델의 한계점을 해결하고, general class of function으로 만들기 위해서 히든레이어를 추가할 수있다.
가장 쉬운방법 중 하나는 가능한한 많은 수의 fully-connected layer를 추가하는 것이다.
