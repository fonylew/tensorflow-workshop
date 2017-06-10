# Introduction

"Artificial Intelligence is new electricity"

Example
- Waymo
- Tensorflow Cart
- Google Cloud Vision API
- Google Cloud Speecch API
- Cucumber sorter

`AI > ML > DL`

A Perceptron
1. Weighted sum : w1, w2, bias
2. Activation Fn : classified class
- Sigmoid
- TanH
- ReLU

http://playground.tensorflow.org

Traditional ML required Feature Engineering

## Training Neural Networks
- Pick an objective/ loss function
-- Cross entropy
   Gradient Descent
- Back-proppagation ปรับยังไงให้ error น้อยลง (Chain Rule)

### Challenges
- learning rate: 
- minibatches (c[j'c[m=N c]h;vyxgf9) vs Stochastic Fradient Descent (random อาจจะติด local minimal)
- Overfitting

### Regularization
- ทำให้ coefficient เข้าใกล้ 0
ใน NN => Dropout 


# Tensorflow
CS20si CS224d
- define Tensorflow Graph
- execute in TensorFlow Runtime

### Pro
- define graph and execute on any platform
- pre-defined derivative operation in Kernels

## What is Tensor?
see TensorFlow Rank
- Rank
- Shape (associated with Rank)
- DataType

### tf.Session()
env ที่ support ให้รันกราฟได้

```
with tf.Session() as sess:
	op3= sess.run(op3)
```
*Execute with dependencies checking (DAG)*

- Operation

## TensorFlow Variables
```

```
- update variable via assign function
- Variables associate with session

#### Variable Scope
`tf.variable_scope('foo')`
`tf.get_variable('v',[1])`

## Placeholder
`a = tf.placeholder(tf.float32, shape=[3])`

to feed data to placeholder => use `feed_dict`
`feed_dict = {a:[1,2,3]}`

# TensorFlow Estimator
ไม่ต้อง create session ทำให้อัตโนมัติ
```
 model_params
     |
instantiate estimator
     |
    fit
     |
score accuracy
  
```
