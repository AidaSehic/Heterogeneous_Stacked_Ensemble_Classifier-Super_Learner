# Heterogeneous Stacked Ensemble Classifier - Super Learner

The <b>Super Learner</b> is a <i>heterogeneous stacked ensemble classifier</i>. This is a classification model that uses a set of <i>base classifiers</i> of <i>different types</i>, the outputs of which are then combined in <i>another classifier</i> at the <i>stacked layer</i>. <br>
The base classifiers are trained and their outputs are combined along with the training dataset labels into a training set for the stack layer classifier. To avoid overfitting the generation of the stacked layer training set uses a <i>k-fold cross validation process</i>. To further add variety to the base estimators a bootstrapping selection is used.
