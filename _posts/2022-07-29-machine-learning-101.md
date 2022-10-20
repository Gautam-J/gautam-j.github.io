---
layout: post
comments: true
mathjax: true
title: Machine Learning 101
excerpt: Learn what exactly is machine learning, and develop an
    intuition behind its workings.
date: 2022-07-29 00:00:00
---

<div class="imgcap">
<img src="/assets/asimo.jpg" height="500px" />
<div class="thecap">
ASIMO. One of the earliest humanoid robots, built by Honda
(2000-2018).
</div>
</div>

### Introduction

The term _Machine Learning_ (ML) has become very popular now. Most people use this
term interchangeably with _Artificial Intelligence_, _Deep Learning_,
_Neural Networks_, _Data Science_, or even _Robotics_. But there is a reason
why we have such specific terms. The main goal of this blog is to make people
aware of what exactly ML is, and to develop an intuition as to how ML works.

### What is Artificial Intelligence?

In order to understand ML, we first need to get ourselves familiar with the
term _Artificial Intelligence_ (AI).
In the 1950s, _John McCarthy_ came up with the term _Artificial Intelligence_.
_Alan Turing_, after solving the Nazi encryption machine _Enigma_, came up with
a simple question that laid the foundation for today's AI
-- Can Machines Think? In 1950, he published the paper _Computing Machinery
and Intelligence_ which introduced the widely popular _Turing Test_.

<div class="imgcap">
<img src="/assets/theimitationgame.jpg" height="300px" />
<div class="thecap">
The Imitation Game (aka The Turing Test), biography of Alan Turing.
</div>
</div>

> Artificial Intelligence is a branch of Computer Science that deals with
> developing algorithms to _mimic_ human intelligence.

"Mimic" is the keyword here. There are
multiple ways to mimic human intelligence. In the book _Artificial Intelligence: A Modern Approach_, the authors
_Stuart Russell_ and _Peter Norvig_ introduce the theme of intelligent agents
in machines, along with different types of AI agents, based on how they
_think_ and _act_ -- **humanly** or **rationally**.

<div class="imgcap">
<img src="/assets/simplereflexagent.png" height="300px" />
<div class="thecap">
Schematic diagram of a Simple Reflex Agent.
</div>
</div>

Thinking and acting humanly is not always possible for an agent. It may not
even lead to an optimal solution. Therefore, we also try to develop agents
that think and act rationally. It chooses the best of all actions, based on
_logical reasoning_. This can give way to developing agents that perform better
than humans, leading to _superintelligence_.

### Machine Learning

> Machine Learning is the field of study that gives computers the ability to
> learn without being explicitly programmed.<br>-- Arthur Samuel (1959)

<div class="imgcap">
<img src="/assets/traditionalvsml.png" height="300px" />
<div class="thecap">
Source: Google I/O 2019
</div>
</div>

In traditional programming, we give a set of rules to the AI agent along with
some information or data. The agent uses its rational thinking capacity and
comes up with a solution. In Machine Learning, we give both the data and the
solution to an agent. The agent analyzes the data, developing a set of rules
by looking at the given solutions.

During _training_ phase, the AI model develops a mapping function that maps
the given data and the solution. This mapping function becomes the set of
rules that we would provide manually to the agent traditionally. Thus, the
AI has learnt those rules without us humans explicitly mentioning the rules.
This mapping function can then be used later during _evaluation_ phase to
come up with solutions for new problems of similar kind.

An important thing to notice here is that ML, although different
from traditional programming, still follows the definition and goal of AI.
_Deep Learning_ (DL) mainly deals with Deep Neural Networks, which itself is a
part of ML.

<div class="imgcap">
<img src="/assets/aimldl.png" height="400px" />
<div class="thecap">
Machine Learning is a subset of Artificial Intelligence. Deep Learning is a
subset of Machine Learning.
</div>
</div>

### A Practical Example: Spam Filtering

In order to get an intuition behind all the theory discussed above, let us take
the example of filtering out irrelevant emails and marking them as spam.
The problem statement is fairly straightforward -- given an email, classify it
as spam or not spam. Let us see how this problem can be solved in different
ways using AI and ML.

#### Approach 1: Traditional Artificial Intelligence

We take a collection of emails. We go through each email, and manually
classify it as spam or not. If it is a spam, we note down why we
think it is spam. It could be because of the following reasons (not restricted):

-   Subject of the email contains offers like "50% off".
-   Address of the email irrelevant such as "abc@marketing.com".
-   It is a phishing email with words like "Congrats! You've won so-and-so".

All these can be made into a set of rules, that we can later feed it to the
agent. Now the agent can apply these set of rules (that we manually came up with)
to new incoming emails and classify it as spam or not spam.

```python
if subject_contains('50% off'):
    mark_as_spam()
```

Do note that traditional AI programming deals with much more complicated
algorithms involving logical reasoning concepts such as boolean algebra and
first order logic.

#### Approach 2: Modern Machine Learning

We again take a collection of emails. We again go through each email, and
manually classify it as spam or not spam. Now, all we have is a dataset of
email with _labels_ that tell whether the email is spam or not. We simply feed
this to a Machine Learning model, and let the model come up with its own set of
rules to correctly match the mappings of the given dataset.

How the ML model learns depends on what algorithm is chosen. For spam filtering,
a popular algorithm to use is _Naive Bayes_. It works on conditional
probability, specifically _Bayes' Theorem_.

$$\Pr(A \mid B)=\frac{\Pr(B \mid A) \cdot \Pr(A)}{\Pr(B)}$$

Naive Bayes model first looks at previous data, and estimates the probability
of an email being spam, given the prior probability of occurrence of words.
For example, the model might come up with a rule such as if the mail contains
the phrase "Congrats!" and "50% off", it will classify it as spam with a certain
probability, say 0.8 or 80%. This depends on the prior probability that it calculated looking at
previous data.

After training the model, we can use the model to classify new incoming emails.

### Conclusion

From the above example, it is clear that traditional AI requires a human to
come up with a set of rules that an agent would follow. In ML, we let the agent
_learn_ the set of rules from a given set of data, hence the name _Machine
Learning_. Think of other examples where you can differentiate both the approaches
clearly for a better understanding. If there are any clarifications, put them down
in the comments.

Happy Learning!
