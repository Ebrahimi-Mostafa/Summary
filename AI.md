# AI

## Table of Contents :bookmark_tabs:

- [University Of Texas Arlington: Neural Networks and Deep Learning](#University-Of-Texas-Arlington:-Neural-Networks-and-Deep-Learning)


<a id="University-Of-Texas-Arlington:-Neural-Networks-and-Deep-Learning"></a>

## University Of Texas Arlington: Neural Networks and Deep Learning
Source:  
https://athitsos.utasites.cloud/courses/cse4392_spring2022/lectures

### Table of Contents :bookmark_tabs:
1. [Introduction to Machine Learning](#Introduction-to-Machine-Learning)


<a id="Introduction-to-Machine-Learning"></a>

### Introduction to Machine Learning

- `What is Machine Learning?`   
    Quote by Tom M. Mitchell: "A computer program is said to learn from
    experience E with respect to some class of tasks T and performance measure P if its performance at tasks in T, as measured by P, improves with experience E."  
- `Define a Machine Learning Problem:`
    - The experience (usually known as training data).
    - The task (classification, regression, ...)
    - The performance measure (classification accuracy, squared error, ...).  
- `Types of Machine Learning:`
    - _Supervised Learning_:  
        - The training data consists of input-output pairs.
        - The task is to learn a function that maps inputs to outputs.
        - The performance measure is the error between the predicted output and the actual output.
    - _Unsupervised Learning_:  
        - The training data consists of input data only.
        - The task is to learn a function that describes hidden structure from the input data.
        - The performance measure is the quality of the learned representation of the input data.
    - _Reinforcement Learning_:  
        - The training data consists of a sequence of states, actions, and rewards.
        - The task is to learn a policy that maps states to actions.
        - The performance measure is the total reward obtained over time.

#### Supervised Learning
- `Classification`:  
    Desire output belongs to a __finite__ number of categories
- `Regression`:  
    Desire output consists of one or more value from a __continuous space__ 

![Classification vs Regression](./rsc/AI/0%20Regression_vs_Classification.jpg.avif)  


#### Unsupervised Learning
- Clustering
- Anomaly Detection
- Reinforcement Learning


#### Reinforcement Learning
- The system needs to explore different actions at different situations, to see what rewards it gets.  
- The system also needs to exploit its knowledge so as to maximize rewards.  
- Example:
    - A robot learns to walk by trying different actions and observing the rewards it gets.
    - A computer program learning how to play a board game, like chess, tic-tac-toe, etc.


#### Model Selection Problem
- Training Error
- Test Error
- Overfitting:  
Model learns the training data too well, and fails to generalize to new data.
- Underfitting
- Ockham's Razor:  
"If you have two competing ideas to explain the same phenomenon, you should prefer the simpler one.


#### Solution to Overfitting
- Some times, our model is too complex and has too many parameters, those parameters are too flexible, and can fit the training data very well. &rarr; Simplify the model.
- our training data is too small, and the model cannot learn the underlying pattern. &rarr; Get more training data.
- Regularization:  
Overfitting leads to very large magnitudes of parameter. &rarr; Add a `regularization term` to the error function to penalize large parameter values.

    ![Error Function with Regularization](https://latex.codecogs.com/svg.image?E(w)&space;=&space;\text{Loss}(w)&space;&plus;&space;\lambda&space;\cdot&space;\text{Regularization}(w))  
    ![lambda](https://latex.codecogs.com/svg.image?\lambda) (lambda) is the regularization parameter, which controls the strength of the regularization. It is a hyperparameter that needs to be set before training.


#### Hyperparameters
- Hyperparameters are parameters that are not learned by the model, but are set before training by us(humans).
- Examples:
    - The number of hidden layers in a neural network.
    - The number of hidden units in each hidden layer.
    - The learning rate.
    - The regularization parameter.
- Choosing hyperparameters:
    - Try different values and see which one works best.
    - Use a validation set to choose the best hyperparameters.

