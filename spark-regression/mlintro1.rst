Machine Learning Introduction 1
===============================

With that backstory in mind, the goal over the upcoming year is to aggregate the expertise throughout Liferay to create a series of workshops will focus on the second question.

**How will users attempt to use DXP and its data to answer important business questions?**

When looking at how data is used to answer questions, one of the tools in that toolbox is machine learning. So, part of our focus in the coming year will be to learn machine learning.

Learning Machine Learning
-------------------------

You've likely heard about machine learning as a concept, and after hearing Jorge talk about it at DEVCON, you might have found yourself wondering, "What's the best way to learn machine learning?"

* `How do I learn machine learning? <https://www.quora.com/How-do-I-learn-machine-learning-1>`__

A few years ago on Quora, someone asked a related question: "What is the best way to learn Galois theory?"

* `What is the best way to learn Galois theory? <https://www.quora.com/What-is-the-best-way-to-learn-Galois-theory>`__

The top answer comes from `Alon Amit <https://www.linkedin.com/in/alonamit>`__, who answered by saying that when learning applied mathematics, nothing beats having a university environment where you wrestle with concepts alongside motivated peers with the guidance of multiple experts. This is especially effective you are tested at the end, challenged to show that you've understood the concepts.

For purposes of our discussion, it's not important to know what Galois theory is beyond the idea that, much like machine learning, it's a branch of applied mathematics. Like Galois theory, it requires a non-trivial familiarity with linear algebra, and with all of the acronyms and strange words, learning it can feel like a foreign language.

* `An Introduction to Galois Theory <https://nrich.maths.org/1422>`__

Like Galois theory, the best way to learn about it is to wrestle with it in a university setting. As such, we won't pretend that this series of workshops can provide a better crash course on performing machine learning than the existing Coursera, Udacity, EdX, or university open courseware on the topic.

* `Stanford: Natural Language Processing with Deep Learning <http://web.stanford.edu/class/cs224n/>`__

Instead, we'll be aiming at the less ambitious second best option, which is to struggle with the concepts alongside our peers. Along the way, we'll look at questions within Liferay that can be answered with machine learning, and we'll see the assumptions that machine learning methods make in attempting to answer those questions.

Workshop Focus
--------------

For today, we'll start with an overview of "deep learning", one of the hot topics you might have heard in passing at DEVCON, and explore some of its benefits and limitations. There are great examples out in the wild that will help you dive deeper into deep learning from a practical perspective, and we'll get started with one of them today.

* `FastAI: Practical Deep Learning For Coders <http://course.fast.ai>`__

At the same time, we'll provide an overview of the simpler machine learning models (just their names and a very brief description) and improve our awareness of what makes them both better and worse than deep learning.

In future workshops, we'll dive deeper both into what makes deep learning work, as well as what makes the simpler machine learning models work so that we understand what our community members and our customers will one day try with Liferay DXP data.

Example Problem
---------------

While we go over the first FastAI course, keep the following question in mind.

Imagine that you're a content developer who has just created a new piece of web content. You've specified a structure, you've created a template, you've embedded beautiful copyright-safe images, and you've identified a page where the web content could appear.

However, let's first ask a business question. How do you know that the web content you created just now belongs on this page and that a different piece of web content written in the past isn't more appropriate?

In order to define appropriateness, you need some form of objective measure that stands in for a business goal. In this case, satisfying of the business need could be success vs. failure, where the occurrence of an event is considered a "success" vs. the non-occurrence of that event is considered a "failure". Examples of this might be conversions, shares on social media. Another business goal could be how well the content relates with all the other elements already on the page.

In a world without machine learning, you'd probably answer based on gut instinct, issuing a few searches, examining a subset of the potential alternatives, and making your decision by tapping into years of knowledge and experience as a content developer. You might also narrow the audience for the article using content targeting in order to boost its apparent relevance.

While this is a valid way to answer this question, let's pretend for a minute that Liferay DXP is a platform that embraces machine learning and data-driven approaches. How might you use machine learning to approach this problem?

Machine Learning Intuition
--------------------------

In a lot of computer science, we understand algorithms by assuming the existence of an oracle machine.

* `Oracle Machine <https://en.wikipedia.org/wiki/Oracle_machine>`__

Put simply, an oracle machine is a black box algorithm where you feed it with inputs and it produces the correct output every time. Essentially, black magic hiding inside of black boxes.

When you design algorithms, essentially you're asking, "Can we create something that isn't a black box that will produce the correct output every time?" We can't be sure. Maybe no oracle machine can be built. Maybe building such an oracle machine is extremely complex and time-consuming.

What if we could step back and ask the question, "Is an almost-oracle good enough?"

* `Obligatory George Box quote <https://en.wikipedia.org/wiki/All_models_are_wrong>`__

In machine learning, you choose a model, you provide some hints as to how the model should initialize, and then you feed the input data into the model. In *supervised learning*, this input data is labeled with what an oracle machine would predict.

The model is programmed to look at its own predictions, compare these to the oracle machine predictions, and then adjust itself to (hopefully) do better the next time around. This process of self-adjustment in order to recreate oracle machine predictions is why all of this is called "machine learning".

* `The Great AI Awakening <http://www.nytimes.com/2016/12/14/magazine/the-great-ai-awakening.html>`__

Example Answer
--------------

So, now that we have a better definition of machine learning, let's come back to our question: how do you know that the web content you created just now belongs on this page and that a different piece of web content written in the past isn't more appropriate?

Imagine that you have all the content metadata surrounding all web content. You have extracted all the text from all web content, all the localizations, and you have textual descriptions of all images. You also have all the categories, hierarchical relationships, as well as information on what links internally to each type of content (how often it showed up in asset publisher or search results).

Imagine that you collected metadata on user events relating to all pages. You know which pages are visited frequently within the same session, and you know the order in which these page visits occur. You know what content traditionally co-occurs within the same page. You also have user sentiment information related to a subset of all page visits, where you know whether they found the content helpful or unhelpful.

Imagine that you collected data on user events relating to all web content. You know which content they visited before they reached that web content, which content they visited after they reached that web content, and you know how they reached each piece of content (email, social media, internal link). You know the time of day, the day of week, the time of year where each event occurred.

Bringing this information and more together, one way you can know if the web content you created belongs on this page if the content is *predicted* to satisfy a defined business need (conversions, shares on social media, similarity to other items already on the page) better than any other content.