Machine Learning Introduction 2
===============================

So now that we've covered the introductory lesson and we've seen a little bit of the explanation that the first lesson of FastAI covered, let's come back to our original motivating question.

**How will users attempt to use DXP and its data to answer important business questions?**

From this first lesson, we know that they will want to clean up their data and organize it in a way that a machine learning model can consume it. Essentially, each example must be consistent, and each example within the training set needs to somehow be labeled (in the lesson case, it was labeled by being placed in a folder).

We also learned that each machine learning model will have some level of confidence associated with each prediction, and that it will have some confidence associated with the classes that it did not report. It's not that the machine learning model is absolutely certain, but rather that it believes that the selected prediction has the highest probability of all known guesses. Conceptually, this is not unlike ranked results in search.

We also learned why there is a big hype for machine learning now rather than in the past.

Improved Hardware
-----------------

You may have heard that in general, machine learning described is a branch of applied mathematics that is essentially a mix of linear algebra and statistics. For this reason, a lot of machine learning education will start by teaching you all of the math that's used in machine learning models, and our ultimate goal is much the same.

* `Linear Algebra Review <http://www.deeplearningbook.org/contents/linear_algebra.html>`__

With that being said, for our immediate purpose, knowing that machine learning is linear algebra and knowing that deep learning is lots of linear algebra explains the surge in interest: over time, it's become much cheaper to perform linear algebra.

About 20 years ago, the state of the art with handling linear algebra was to create so-called supercomputers that were good at performing operations on vectors. These specialized machines were called vector processors and they were extremely expensive.

* `Vector Processors <https://www.phy.ornl.gov/csep/ca/node24.html>`__

About 10 years ago, something happened which unexpectedly caused a stir in the scientific computing community: the release of the Sony Playstation 3. It turns out that video games use linear algebra in order to act on objects in three-dimensional space, and so video game consoles become highly optimized for this task. Effectively, the release of the Sony Playstation 3 gave researchers access to commodity hardware that provided capabilities that are very similar to vector processors in the form of the cell processor, but at a fraction of the cost.

* `The Playstation 3 for High Performance Scientific Computing <https://pdfs.semanticscholar.org/57a5/d7ce9ff326873a6b505184ef3c21457ef7c2.pdf>`__

Moving forward in time, graphics card developers were increasing the capabilities of their graphics cards so you could perform arbitrary matrix transformations, effectively giving game developers a lot more flexibility in the transformations that could happen on screen. Leveraging this flexibility, a variety of vendors figured out how to create supercomputers by designing high bandwidth connections between video cards.

* `Deep Learning: Applications <http://www.deeplearningbook.org/contents/applications.html>`__

Fast forward to the modern day. With Amazon, Microsoft, and Google providing access to clusters of servers equipped with these graphics cards in the cloud, you don't even have to own the hardware but simply ask for access to these servers you need as you need them.

Essentially, we've reached a point where you can perform linear algebra operations at extremely high speeds at extremely low cost. As a result, machine learning is no longer prohibitively expensive to run, and so even deep learning is now accessible to people outside the scientific computing community.

Open Source Culture
-------------------

Freely-available technology is moving things forward in the deep learning space. In the lesson that we watched, people are excited to share that there are a large number of tutorials and question/answer guides surrounding ``numpy`` and ``matplotlib``. We build upon the drivers provided by NVIDIA for large scale linear algebra. We interact with Jupyter notebooks, which are themselves presentations of all the source code involved with the research.

However, as we all know, open source means a lot more than simply releasing source code. As you've likely heard from all of the open source advocates within Liferay, the notion of "open source" is both social and technological. It's recognized equally for the documentation and the raw quality of the technical solution.

* `Rules of Machine Learning <http://martin.zinkevich.org/rules_of_ml/rules_of_ml.pdf>`__

A culture of open source within the machine learning community has helped push deep learning forward. An open source culture is one where developers are excited to spread the news on how they achieved a result. All this is provided with the hope that others within the open source community will be able to replicate your success (reproducible research) or build upon your success in order to solve their own unique problems.

The matured community is a reason for why Keras and Theano are preferrable to Tensorflow. The open sourcing of both the weights and the components of the Vgg16 neural network model allowed us to springboard, even though Vgg16 was originally intended for the broader task of ImageNet.

Without all of this buzz and excitement, deep learning would probably still be buried within large technology companies instead of being spread throughout the industry, and our key message of "insight" would fall on deaf ears.