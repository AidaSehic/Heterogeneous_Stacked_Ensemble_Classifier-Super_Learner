# Heterogeneous Stacked Ensemble Classifier - Super Learner

The <b>Super Learner</b> is a <i>heterogeneous stacked ensemble classifier</i>. This is a classification model that uses a set of <i>base classifiers</i> of <i>different types</i>, the outputs of which are then combined in <i>another classifier</i> at the <i>stacked layer</i>. <br>
The base classifiers are trained and their outputs are combined along with the training dataset labels into a training set for the stack layer classifier. To avoid overfitting the generation of the stacked layer training set uses a <i>k-fold cross validation process</i>. To further add variety to the base estimators a bootstrapping selection is used.

In this project I have:
1. Wrote a SuperLearnerClassifier Python class that implements the Super Learner algorithm with the following characteristics:
* It has a fixed set of 6 base heterogeneous models.
* It has sensible default hyper-parameters for these base estimators.
* It generates the stacked layer training set using the label outputs from the base estimators.
* It uses a decision tree model at the stacked layer.

2. Evaluated the performance of the Super Learner using a 10-fold cross validation on the MNIST fashion training dataset available from Kaggle at https://www.kaggle.com/zalando-research/fashionmnist .
(I have used the scikit-learn function sklearn.model_selection.cross_val_score to perform the cross validation.
Also, I have used Classification accuracy as the performance measure for the evaluation.)

3. Modified the implementation so that the SuperLearnerClassifier constructor can take a parameter indicating whether the stacked layer classifier should be trained on label outputs from the base classifiers or probability outputs from the base classifiers.

4. Modified the implementation so that the SuperLearnerClassifier constructor can take a parameter to specify the type of model to use at the stack layer

5. Performed an evaluation experiment comparing the performance of the model using label outputs to train the stack layer and a model using probability outputs to train the stack layer.
• Choose an appropriate experimental method and performance measure.
• Experiment with both decision trees and logistic regression models at the stack layer.
• Keep the base estimators specification and any other parameters constant for this experiment.
 
6. Modify the implementation so that the SuperLearnerClassifier constructor can take a parameter to specify the base estimators to use.
• This could be reasonably specified in different ways - for example, as a specific list of exactly the base estimator model types to use or a list of allowed base estimator types and an overall number of base estimators in the ensemble to be created based on this list.
• It is sensible to limit the types of base estimators that the algorithm can use to a sensible set of 5 - 10 algorithms from scikit- learn.
• It is not required to also specify hyper-parameters for each algorithm, use a default set.
7. Perform a grid search to determine the best setup (e.g. base estimators, stack layer model, stack layer training data type, etc) for the Super Learner.
8. It has been suggested that also adding the original input to the input at the stack layer could improve the Super Learner. Implement a modification that includes this and evaluate its impact.
• Use the best setup found in Task 7.
9. Ensemble models rely on the base estimators being strong predictors but
at the same time weakly correlated with each other. Implement some functionality to show the extent to which the estimators in your model satisfy these criteria?
