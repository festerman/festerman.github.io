---
layout: post
title:  "PopMEB NG, first steps (experimenting!)"
date:   2017-01-03 13:44:43
categories: node express rest epidemiology DDD
---
## Why?

The place I work is heavily into Medical Epidemiology, and I'm in charge
of the databases they use. These have a lot of medical and lifestyle data,
and different versions of the same data.

To enable researchers and students to find the data they need for their
thing, we have something called a **data dictionary**. Each study/dataset/project should have one. This essentially describes what's
in the dataset.

In addition, "_the authorities_" require us to keep track of what kind
of stuff we store, and to **show** that we keep track of the data.

So we'll want to combine all the data dictionaries into one big **data dictionary** thingie, that researchers can use to find what they need, and that the govmint can look at and say that "_OK, that looks tidy and nice_".

And finally, I want to experiment a bit with javascript, Node, REST and single page apps, and NoSQL databases ...

## Some domain stuff

* **Dataset**

  A number of **observations**. Each observation is usually tied to (of) a member of a **cohort**. A dataset can be used in a **study**.

  In practical life, a dataset is one or more tables in a relational database.

* **Observation**

  An observation consists of some kind of measurement of a set of **variables** at a point in time.

  An observation may be a set of answers to a questionnaire, or diagnosis records from a health quality register.

  These are the rows in the table.

* **Variable**

  The individual measurements from an **observation**.

  A variable may be one of the answers to the questions in a questionanaire. Example questions are

  * How many cigarettes do you smoke per day?
  * Did your father die of prostate cancer?

  <br/>
  In the database, these are the columns in the table.

* **Cohort**

  A group of individuals sharing something: a diagnosis, a birthyear, ...

* **Study**

  This is what epidemiology does. In science theory terms this is a hypothesis, and the tests done to prove (or disprove) it.

  In real life, the outcome is usually a scientific article, or a PhD thesis.

## Basic ideas

This is an experiment for my education, so it will be pretty fluid. But basically, what it will be is:

* a server with a REST API. First version will be using Express in a Node server.
* database will be a MongoDB instance.
* tests! Full test coverage is the goal. BDD + TDD!
* single-page app in (probably) Angular.

I'll start with getting a very basic server going.  
