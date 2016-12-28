Machine Learning Introduction 3
===============================

The image classification example isn't just because so many problems map into it. As you've seen from the lesson, it's also ideal because it's easy to visualize what the convolutional neural network would do to an image, and then use that to understand how these neural networks work in other domains.

* `Forward Propagation: Building a Skip-Gram Net From the Ground Up <http://blog.districtdatalabs.com/nlp-research-lab-part-3-forward-propagation-1>`__

Another really great example of convolutional neural networks is provided in a Medium post.

* `Machine Learning is Fun, Part 3 <https://medium.com/@ageitgey/machine-learning-is-fun-part-3-deep-learning-and-convolutional-neural-networks-f40359318721#.n7rhoktr8>`__

What this boils down to is if your final classification result is a complex concept, and if you know that simpler concepts can come together and snowball into your final classification result, deep learning addresses your classification problem by attempting to learn the concepts that come together in order to perform the classification.

* `Neural Networks: A (Very) Light Introduction <http://machinelearningalgorithmsillustrated.azurewebsites.net>`__

Ensemble Methods
----------------

Imagine you were told that you needed to create a team of Liferay engineers working on creating a digital experience platform.

In theory, what you can set as a goal is to identify the absolute best engineer and attempt to clone their skillset a thousand times in order to form a small army of identically skilled developers. However, there is one important limitation with this strategy: there is no such thing as engineer who is good at seeing a system from all perspectives, because life experiences don't work like that.

Instead, a goal of many corporations is to recruit people from a diverse set of backgrounds in order to have a more complete perspective of the problems and challenges the corporation must face.

Within machine learning, there are a variety of models you can use as almost-oracles. Each of them takes in different types of information, makes different assumptions, and produces different results. Even if you were to narrow your focus to something as seemingly specific as deep learning, each model will vary the way it treats the available information in order to become better at specific tasks.

However, just as is the case when building a company,

In machine learning, the process of combining a diverse set of algorithms together into a team of algorithms is referred to as creating an ensemble model.

* `Model Stacking in Practice <http://blog.kaggle.com/2016/12/27/a-kagglers-guide-to-model-stacking-in-practice/>`__

Machine Learning Basics
-----------------------

Deep learning makes a few assumptions about the data. First, it assumes that it's okay to have a black box interpretation where optimizing some metric related to the prediction (accuracy, recall, precision) is acceptable, or that there are tools that give you a good sense of what the model is actually predicting.

* `Local Interpretable Model-Agnostic Explanations <https://github.com/marcotcr/lime>`__

However, for a variety of reasons, a non-transparent model might not be desirable from a legal perspective, because they are hard to interpret, and instead, you would strongly prefer a model that is extremely easy to interpret compared to other models. You may also want a model that is similar to what others in the industry are using in order to protect yourself via previously set precedents.

* `Supersparse Linear Integer Models <https://arxiv.org/pdf/1502.04269.pdf>`__

So now that you've seen a crash course on deep learning, we'll talk briefly about some of the key assumptions made by some of the introductory machine learning algorithms that would be introduced in a mathematics-first approach to machine learning. Our goal is that throughout the year, we'll be creating trainings to help you understand them intuitively, but for now we'll list a handful of them so that you get a sense that they exist.

Linear Regression
~~~~~~~~~~~~~~~~~

Linear regression makes a lot of assumptions about the data in order to make it BLUE (best linear unbiased estimator) that requires both math to understand (the definition of "unbiased", for example) and time to let that understanding sink in. If you happen to know an economist or a social scientist, this is among the very first predictor models they learn, and it only gets scarier from there.

* `Linear State Space Models <http://lectures.quantecon.org/jl/linear_models.html>`__
* `A Complete Tutorial on Time Series Modeling in R <https://www.analyticsvidhya.com/blog/2015/12/complete-tutorial-time-series-modeling/>`__

In linear regression, the assumption is that for any feature, if you were to increase one of the features by 1 and leave all other features constant, there is, on average, a fixed change in the value you're predicting. If you increase it by 1 again while leaving all other features constant, the same on-average fixed change occurs in the value you're predicting. The same applies to all features.

You might think this makes it really limiting, but when you think about it, almost all mathematical functions are essentially saying the same thing. You could derive new variables based on the existing ones (multiply them together, take logarithms or square roots, etc.), and the coefficient still says that a one unit increase in that derived variable results in a fixed change in the value you are predicting. It's just that you can't vary that variable by itself in practice.

Decision Trees
~~~~~~~~~~~~~~

Decision trees make the same sort of assumption as linear regression in that "on average" (or in the case of classification, the plurality) is a good measure, but rather than looking at unit changes, it creates bins for the values. So, rather than using the features to predict values, you use the features to divide the data into groups, and what your almost oracle predicts for any given data point is the known average of all the members for that data point's group.

* `A simple explanation of how entropy fuels a decision tree model <http://www.simafore.com/blog/bid/94454/A-simple-explanation-of-how-entropy-fuels-a-decision-tree-model>`__

The goal of decision trees is to divide them feature by feature into groups where the differences between groups is large, but the elements within the group are very similar to each other. Naturally this is hard, so a common extension of decision trees is to randomly choose subsets of features and make lots of decision trees, bringing them together under an ensemble model. This ensemble model is known as a random forest.

Naive Bayes
~~~~~~~~~~~

Naive Bayes makes the same "on average" assumption as linear regression and decision trees, but it takes on the Bayesian view of the world and uses a belief system.

* `XKCD: Frequentists vs. Bayesians <https://xkcd.com/1132/>`__

The idea is that if every feature's value is completely independent from every other feature's value, you might be able to perform predictions based on the idea of an "updated belief". As each feature is observed, you become more confident if it happens frequently with the outcome and you become less confident if it happens infrequently with the outcome. Your almost oracle then tells you how confident it is based on the data it has seen.

This is most commonly taught in the context of spam filtering, where the features are the presence or counts of words.

K-Means Clustering
~~~~~~~~~~~~~~~~~~

The intuition behind k-means clustering is essentially similar to a decision tree, except rather than explicitly saying that features cleanly divide each other, you say that the groups are slightly more subtle. As a result, you guess how many groups there are and the algorithm will try to find the centers of mass for those groups. Again, your almost oracle would guess the average (or the plurality) for the group.

* `Understanding K-means Clustering With Examples <https://www.edureka.co/blog/k-means-clustering/>`__

The intuition is that idea is if you have a vague idea that there are "clusters" where data points are, and that these clusters actually relate to your outcome variable. You know whether your almost oracle is the best almost oracle simply by trying a lot of different group counts and confirming that your optimal number of groupings performed better than all your other guesses on the number of groups.
