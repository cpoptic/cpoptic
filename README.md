<!--
**cpoptic/cpoptic** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
-->

### Hi there

So GitHub recently enabled personal GitHub READMEs, which I think is a great idea.  I've been wanting an excuse to start writing about things I work on and things I've been learning and reading, and this is a perfect reason to start:  it combines my love of all things Data Science with my love of writing and teaching/explaining concepts to people.

- 🔭 I’m currently working on computer vision projects (2D, 3D, video), time-series forecasting, NLP tasks like sentiment analysis on alternative data sources via Transformer models, and applying deep learning techniques to good ol' fashioned tabular datasets, signal processing, AutoML
- 🌱 I’m currently learning pytorch_tabnet, NLP tasks with BERT, how to classify pulmonary embolisms from 3D CT medical image data for the Kaggle compeition.

- 💬 You can often find me ... learning some new machine learning technique, reading and writing code, thinking about how to solve a problem I'm working on while riding my bike.
- 📫 How to reach me: ... chris dot poptic @ gmail dot com
- ⚡ Fun fact: I logged over 10,000 miles riding my bike and won the Ohio State Road Race Championship a few years back.

-- A few blogs I follow (more to come as I add to this list):

[Sebastian Raschka's excellent blog](https://sebastianraschka.com/) 
Also, [Follow him on Twitter](https://twitter.com/rasbt)




## TODAY I LEARNED / THINGS I'M READING

### 2020-09-14

One thing that we ML engineers must prioritize is writing "production-ready code".  That term has been thrown around a lot, and for good reason; code that integrates well with an app and can be used by a) other devs on your team or b) end-users  is the only type of code that ultimately brings "value" to an organization.

BTW, an excellent book on this topic is Ben G Weber's "Data Science in Production: Building Scalable Model Pipelines with Python".  Highly recommend.  In Ben's words:
> The general theme of the book is to take simple machine learning models and to scale them up in different configurations across multiple cloud environments

Ben continues:
> Putting predictive models into production is one of the most direct ways that data scientists can add value to an organization. 
> By learning how to build and deploy scalable model pipelines, data scientists can own more of the model production process and rapidly deliver data products.


Another important concept is API-first design.  This is related to [Writing Software from the Outside In](https://medium.com/@jejo.math/writing-software-from-the-outside-in-e5359f60fa30), explained in another excellent blog post by Jesse Johnson.

It's easy to crank out an quick data anslysis or moddel of code that works, but has no way of "talking" with the rest of your system/app.

One phenomena any machine learning engineer has experienced is "Tech Debt".  If you haven't heard of tech debt, it's fairly self-explanatory.


What contributes to complexity?
> One of the most important techniques for managing software complexity is to design systems so that developers only need to face a small fraction of the overall complexity at any given time. 
- John Ousterhout

This is so true.  On a large project, the only way to stay organized and keep your sanity is to leverage the object-oriented principle of abstraction.
Functions are your friend here.  If you find a block of related code that is used more than once, then follow Guido's Python programming language of D.R.Y. and Don't Repeat Yourself.  Wrap that code in a function, cut and paste it into your utilities file, and do an import of it in your notebook.

David Tan speaks in detail about this in yet another blog post I highly recommend to any junion aspiring data scientist.
https://www.thoughtworks.com/insights/blog/coding-habits-data-scientists

David Tan recommends a good software engineering practice of having a goal of moving your code out of your Jupyter notebook ASAP.
By doing so, we accomplish three things:

1)  You reduce the cognitive load that we, as developers, experience when trying to hold a bunch of complex operations in our mind.
2)  You enable that chunk of code to be unit-tested (see Test-Driven Development), which gives you more confidence in the code you write.
3)  You make that chunk of code more reusable, not only by you, but by any other members of your project's team.  Save them time from re-inventing the wheel; they can simply import your library and use the function you wrote.



### 2020-09-15

The upcoming Nvidia 3000-series GPUs have me pretty excited to train deep learning models more quickly and efficiently.  Especially the massive 24 GB of VRAM on the RTX 3090, which will make training big Transformer models actually feasible for modern NLP tasks.

Because there's so much marketing hype surrounding the Ampere release and because, as a principle, I believe in trusting people's opinion to be more informed than mine if they are more experienced in an area (as any good Bayesian would), I read through a [blog post](https://timdettmers.com/2020/09/07/which-gpu-for-deep-learning/) by Tim Dettmers on choosing a GPU for your next deep learning PC.  Tim has an excellent analysis on the topic, which I highly recommend.

A great webinar today by Thomas Ott, Customer Solutions Engineer/Business Data Scientist at H2O.ai called "Real AI Transformation: Getting Models Into Production"
Some key takeaways:
*"What makes companies successful is getting models into production"*

### 2020-09-21

Watched an excellent talk from AIDevFest20 on [Machine Learning Design Patterns for MLOps](https://www.youtube.com/watch?v=_Ni6JWdeCew&ab_channel=AICamp) by Valliappa Lakshmanan.  This is such an important topic in the life of a machine learning engineer, and addresses a major pain-point in our daily work.
I'm looking forward to reading his book, "Machine Learning Design Patterns", to be released in November 2020.

Some key points:
- An ML workflow has all the dev challenges of ensuring things are repeatable, but also the added challenges during production of ensuring you can continuously retrain and serve a model.
- How to resolve these challenges?  Consider your workflow as a pipeline.  This pipeline is an executable DAG of ML steps.
- Each of those steps is a container 
-- data pre-processing and validation container, 
-- feature enginering container, 
-- train XGBoost model container, 
-- train LGB model container, 
-- evaluate model container
-- deploy model container
-- etc
- These pipeline steps (containers) are not independent, but rather are _connected_.  Like a network graph.  Indeed, a directed graph.  A directed graph where no subgraphs are cyclical such that you get caught in an endless loop  (i.e. a Directed Acyclic Graph).  
-- Use dependency tracking:  the output of each step in the pipeline is an artifact.
- The output of one step is an artifact, which becomes the input of the subsequent step.

- Google TFX
Obviously, being employees of Google, they're biased towards Google products, but TFX is a great tool for this.
