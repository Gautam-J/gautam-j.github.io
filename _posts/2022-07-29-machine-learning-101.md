---
layout: post
comments: true
mathjax: true
title: Machine Learning 101
excerpt: Learn what exactly is machine learning, and develop an
  intuition behind its workings.
date: 2022-07-29 00:00:00 +0530
permalink: /:title
---

<div class="imgcap">
<img src="/assets/asimo.jpg" height="500px" />
<div class="thecap">
ASIMO. One of the earliest humanoid robots, built by Honda
(2000-2018).
</div>
</div>

### Introduction

The term *Machine Learning* (ML) has become very popular now. Most people use this
term interchangeably with *Artificial Intelligence*, *Deep Learning*,
*Neural Networks*, *Data Science*, or even *Robotics*. But there is a reason
why we have such specific terms. The main goal of this blog is to make people
aware of what exactly ML is, and to develop an intuition as to how ML works.

### What is Artificial Intelligence?
In order to understand ML, we first need to get ourselves familiar with the
term *Artificial Intelligence* (AI).
In the 1950s, *John McCarthy* came up with the term *Artificial Intelligence*.
*Alan Turing*, after solving the Nazi encryption machine *Enigma*, came up with
a simple question that laid the foundation to today's AI
-- Can Machines Think? In 1950, he published the paper *Computing Machinery
and Intelligence* which introduced the widely popular *Turing Test*.

<div class="imgcap">
<img src="/assets/theimitationgame.jpg" height="300px" />
<div class="thecap">
The Imitation Game (aka The Turing Test), biography of Alan Turing.
</div>
</div>

> Artificial Intelligence is a branch of Computer Science that deals with
developing algorithms to *mimic* human intelligence.

"Mimic" is the keyword here. There are
multiple ways to mimic human intelligence. In the book *Artificial Intelligence: A Modern Approach*, the authors
*Stuart Russell* and *Peter Norvig* introduce the theme of intelligent agents
in machines, along with different types of AI agents, based on how they
*think* and *act* -- **humanly** or **rationally**.

<div class="imgcap">
<img src="/assets/simplereflexagent.png" height="300px" />
<div class="thecap">
Schematic diagram of a Simple Reflex Agent.
</div>
</div>

Thinking and acting humanly is not always possible for an agent. It may not
even lead to an optimal solution. Therefore, we also try to develop agents
that think and act rationally. It chooses the best of all actions, based on
*logical reasoning*. This can give way to developing agents that perform better
than humans, leading to *superintelligence*.

### Machine Learning

> Machine Learning is the field of study that gives computers the ability to
learn without being explicitly programmed.<br>-- Arthur Samuel (1959)

<div class="imgcap">
<img src="/assets/traditionalvsml.png" height="300px" />
<div class="thecap">
Source: Google I/O 2019
</div>
</div>

In traditional programming, we give a set of rules to the AI agent along with
some information or data. The agent uses its rationaly thinking capacity and
comes up with a solution. In Machine Learning, we give both the data and the
solution to an agent. The agent analyzes the data, developing a set of rules
by looking at the given solutions.

During *training* phase, the AI model develops a mapping function that maps
the given data and the solution. This mapping function becomes the set of
rules that we would provide manually to the agent in traditionally. Thus, the
AI has learnt those rules without us humans explicitly mentioning the rules.
This mapping function can then be used later during *evaluation* phase to
come up with solutions for new problems of similar kind.

An important thing to notice here is that ML, although different
from traditional programming, still follows the definition and goal of AI.
*Deep Learning* (DL) mainly deals with Deep Neural Networks, which itself is a
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
The problem statement is fairly straight forward -- given an email, classify it
as spam or not spam. Let us see how this problem can be solved in different
ways using AI and ML.

#### Approach 1: Traditional Artificial Intelligence

We take a collection of emails. We go through each email, and manually
classify it whether it is a spam or not. If it is a spam, we note down why we
think it is a spam. It could be because of the following reasons (not restricted):
- Subject of the email contains offers like "50% off".
- Address of the email irrelevant such as "abc@marketing.com".
- It is a phishing email with words like "Congrats! You've won so and so".

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
email with *labels* that tell whether the email is spam or not. We simply feed
this to a Machine Learning model, and let the model come up with its own set of
rules to correctly match the mappings of the given dataset.

How the ML model learns depends on what algorithm is chosen. For spam filtering,
a popular algorithm to use is *Naive Bayes*. It works on conditional
probability, specifically *Bayes' Theorem*.

$$\Pr(A \mid B)=\frac{\Pr(B \mid A) \cdot \Pr(A)}{\Pr(B)}$$

Naive Bayes model first looks at previous data, and estimates the probability
of an email being spam, given the prior probability of occurence of words.
For example, the model might come up with a rule such as if the mail contains
the phrase "Congrats!" and "50% off", it will classify it as spam with a certain
probability, say 0.8 or 80%. This depends on the prior probability that it calculated looking at
previous data.

After training the model, we can use the model to classify new incoming emails.

### Conclusion

From the above example, it is clear that traditional AI requires a human to
come up with a set of rules that an agent would follow. In ML, we let the agent
*learn* the set of rules from a given set of data, hence the name *Machine
Learning*. Think of other examples where you differentiate both the approaches
clearly for a better understanding. If there are any clarifications, put them down
in the comments.

Happy Learning.
