# 1 pixel attack on LeNet

Artificial perturbations can make DNNs misclassify an image. In this attack we create 1 pixel perturbation to an naturally occurring image that may be hard for a human eye to identify but can make a DNN miss classify the image. This project is based on research One pixel attack for fooling deep neural networks.
The attack uses a Differential evolution method for optimizing our solution. This has many benefits over traditional methods like doesn't need differentiable functions, and is not concerned about the kind of input. DE also is very transparent and hence makes it very easy to tracing the steps and fine tuning the algorithm.
xi =xa+F(xb-xc)
Where a,b,c are different and i and a are also different. And a,b,c are randomly chosen from the sample set.

The method works as first the initial population is imputed into the algorithm and it mutates each element according to the above criteria. After mutating each element from the population recombination occurs, and followed by selection depending upon fitness relative to its previous generation. Then it is finally checked if the attack is successful. This is done via a callback function which checks if the first element from the population gives the desired result. If yes then the DE is terminated and a solution is given. If not then this process keeps on going until a solution is reached or given number iterations have been completed.

In our attack the DE is given perturbations in form of a tuple of length 5 (x,y,r,g,b) which has coordinates and rgb value of the perturbation. Then it returns the most optimized solution from a population of 400.

Success rate for my attack is 6 percent.



This code shows the how simple it is to attack DNN and make it misclassify an object. This attack make just 1 pixel change to the data.
The output of the attack is shown in temp.csv
where the first coloum shows the image id then next shows the true class, then predicted class, and then the suucess of attack.
