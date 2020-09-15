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

2020-09-14

One thing that we ML engineers must prioritize is writing "production-ready code".  That term has been thrown around a lot, and for good reason; code that integrates well with an app and can be used by a) other devs on your team or b) end-users  is the only type of code that ultimately brings "value" to an organization.

How easy it is to crank out an exploratory data anslysis of code that works, but whose barrier to incorporation into a larger codebase is rather high.

One phenomena any machine learning engineer has experienced is good ol Tech Debt.  If you haven't heard of tech debt, it's fairly self-explanatory


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



2020-09-15

The upcoming Nvidia 3000-series GPUs have me pretty excited to train deep learning models more quickly and efficiently.  Especially the massive 24 GB of VRAM on the RTX 3090, which will make training big Transformer models actually fasible for modern NLP tasks.

Because there's so much marketing hype surrounding the Ampere release and because, as a principle, I believe in trusting people's opinion to be more informed than mine if they are more experienced in an area (as any good Bayesian would), I read through a [blog post](https://timdettmers.com/2020/09/07/which-gpu-for-deep-learning/) by Tim Dettmers on choosing a GPU for your next deep learning PC.  Tim has an excellent analysis on the topic, which I highly recommend.
