# Decision Tree
Algo intro - TBD

* We can tell apart a dog from a cat immediately with a glance, but what if we cannot see the whole picture, we are just allowed to ask yes or no questions??

* This is basically the main idea of decision tree.

* Discuss a little about find_best_question, give program flow chart

* Discuss Simple Decision tree performance

* Acc = 63

![image](https://github.com/frostace/BinaryClassification/blob/master/Algo2%20-%20Decision%20Tree/Decision%20Tree%20ACC.png)

* ROC = 0.669

![image](https://github.com/frostace/BinaryClassification/blob/master/Algo2%20-%20Decision%20Tree/Decision%20Tree%20ROC.png)

* F1-meas = TBD



### bug track
1. Looks good, but cutoff is not working, try printing true rate values
	* Overfitting, i changed the gini convergence condition to gini <= 0.01, to make it converge fast

2. Imbalanced input data, the algo is cheating to reach an acc of 74.7%, which is the original distribution of label0 in the dataset
	* F-measure = 0.284839
	
![image](https://github.com/frostace/BinaryClassification/blob/master/Algo2%20-%20Decision%20Tree/Imbalance%20Data.png)

3. there exist a situation s.t. a question can increase the gini info instead of decreasing it or at least keeping it remain
	* it's normal
	
4. find_best_question function is considering 'CLASS' column as an attribute to try to raise a question
	* removed 'CLASS' column from training attribute

5. when raising a question, we should skip meaningless reference values like 'null' and 'nan', etc.

6. when answering a question, say, trying to compare 'null' to a certain reference value is meaningless
	* we should roll a dice to decide, which branch to go to cancel the influence of null values
