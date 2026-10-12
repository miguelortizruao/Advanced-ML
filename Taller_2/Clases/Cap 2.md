

<!-- Pagina 35 -->
correlations or new trends, and thereby lead to a better understanding of the prob‐
lem. Applying ML techniques to dig into large amounts of data can help discover pat‐
terns that were not immediately apparent. This is called data mining.
Figure 1-4. Machine Learning can help humans learn
To summarize, Machine Learning is great for:
• Problems for which existing solutions require a lot of fine-tuning or long lists of
rules: one Machine Learning algorithm can often simplify code and perform bet‐
ter than the traditional approach.
• Complex problems for which using a traditional approach yields no good solu‐
tion: the best Machine Learning techniques can perhaps find a solution.
• Fluctuating environments: a Machine Learning system can adapt to new data.
• Getting insights about complex problems and large amounts of data.
Examples of Applications
Let’s look at some concrete examples of Machine Learning tasks, along with the tech‐
niques that can tackle them:
Analyzing images of products on a production line to automatically classify them
This is image classification, typically performed using convolutional neural net‐
works (CNNs; see Chapter 14).
Examples of Applications 
| 
5


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0035_img_01.png)

<!-- Pagina 36 -->
Detecting tumors in brain scans
This is semantic segmentation, where each pixel in the image is classified (as we
want to determine the exact location and shape of tumors), typically using CNNs
as well.
Automatically classifying news articles
This is natural language processing (NLP), and more specifically text classifica‐
tion, which can be tackled using recurrent neural networks (RNNs), CNNs, or
Transformers (see Chapter 16).
Automatically flagging offensive comments on discussion forums
This is also text classification, using the same NLP tools.
Summarizing long documents automatically
This is a branch of NLP called text summarization, again using the same tools.
Creating a chatbot or a personal assistant
This involves many NLP components, including natural language understanding
(NLU) and question-answering modules.
Forecasting your company’s revenue next year, based on many performance metrics
This is a regression task (i.e., predicting values) that may be tackled using any
regression model, such as a Linear Regression or Polynomial Regression model
(see Chapter 4), a regression SVM (see Chapter 5), a regression Random Forest
(see Chapter 7), or an artificial neural network (see Chapter 10). If you want to
take into account sequences of past performance metrics, you may want to use
RNNs, CNNs, or Transformers (see Chapters 15 and 16).
Making your app react to voice commands
This is speech recognition, which requires processing audio samples: since they
are long and complex sequences, they are typically processed using RNNs, CNNs,
or Transformers (see Chapters 15 and 16).
Detecting credit card fraud
This is anomaly detection (see Chapter 9).
Segmenting clients based on their purchases so that you can design a different marketing
strategy for each segment
This is clustering (see Chapter 9).
Representing a complex, high-dimensional dataset in a clear and insightful diagram
This is data visualization, often involving dimensionality reduction techniques
(see Chapter 8).
Recommending a product that a client may be interested in, based on past purchases
This is a recommender system. One approach is to feed past purchases (and
other information about the client) to an artificial neural network (see Chap‐
6 
| 
Chapter 1: The Machine Learning Landscape

<!-- Pagina 37 -->
ter 10), and get it to output the most likely next purchase. This neural net would
typically be trained on past sequences of purchases across all clients.
Building an intelligent bot for a game
This is often tackled using Reinforcement Learning (RL; see Chapter 18), which
is a branch of Machine Learning that trains agents (such as bots) to pick the
actions that will maximize their rewards over time (e.g., a bot may get a reward
every time the player loses some life points), within a given environment (such as
the game). The famous AlphaGo program that beat the world champion at the
game of Go was built using RL.
This list could go on and on, but hopefully it gives you a sense of the incredible
breadth and complexity of the tasks that Machine Learning can tackle, and the types
of techniques that you would use for each task.
Types of Machine Learning Systems
There are so many different types of Machine Learning systems that it is useful to
classify them in broad categories, based on the following criteria:
• Whether or not they are trained with human supervision (supervised, unsuper‐
vised, semisupervised, and Reinforcement Learning)
• Whether or not they can learn incrementally on the fly (online versus batch
learning)
• Whether they work by simply comparing new data points to known data points,
or instead by detecting patterns in the training data and building a predictive
model, much like scientists do (instance-based versus model-based learning)
These criteria are not exclusive; you can combine them in any way you like. For
example, a state-of-the-art spam filter may learn on the fly using a deep neural net‐
work model trained using examples of spam and ham; this makes it an online, model-
based, supervised learning system.
Let’s look at each of these criteria a bit more closely.
Supervised/Unsupervised Learning
Machine Learning systems can be classified according to the amount and type of
supervision they get during training. There are four major categories: supervised
learning, unsupervised learning, semisupervised learning, and Reinforcement
Learning.
Types of Machine Learning Systems 
| 
7

<!-- Pagina 38 -->
1 Fun fact: this odd-sounding name is a statistics term introduced by Francis Galton while he was studying the
fact that the children of tall people tend to be shorter than their parents. Since the children were shorter, he
called this regression to the mean. This name was then applied to the methods he used to analyze correlations
between variables.
Supervised learning
In supervised learning, the training set you feed to the algorithm includes the desired
solutions, called labels (Figure 1-5).
Figure 1-5. A labeled training set for spam classification (an example of supervised
learning)
A typical supervised learning task is classification. The spam filter is a good example
of this: it is trained with many example emails along with their class (spam or ham),
and it must learn how to classify new emails.
Another typical task is to predict a target numeric value, such as the price of a car,
given a set of features (mileage, age, brand, etc.) called predictors. This sort of task is
called regression (Figure 1-6).1 To train the system, you need to give it many examples
of cars, including both their predictors and their labels (i.e., their prices).
In Machine Learning an attribute is a data type (e.g., “mileage”),
while a feature has several meanings, depending on the context, but
generally means an attribute plus its value (e.g., “mileage =
15,000”). Many people use the words attribute and feature inter‐
changeably.
Note that some regression algorithms can be used for classification as well, and vice
versa. For example, Logistic Regression is commonly used for classification, as it can
output a value that corresponds to the probability of belonging to a given class (e.g.,
20% chance of being spam).
8 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0038_img_01.png)

![Figura](images/page_0038_img_02.png)

<!-- Pagina 39 -->
2 Some neural network architectures can be unsupervised, such as autoencoders and restricted Boltzmann
machines. They can also be semisupervised, such as in deep belief networks and unsupervised pretraining.
Figure 1-6. A regression problem: predict a value, given an input feature (there are usu‐
ally multiple input features, and sometimes multiple output values)
Here are some of the most important supervised learning algorithms (covered in this
book):
• k-Nearest Neighbors
• Linear Regression
• Logistic Regression
• Support Vector Machines (SVMs)
• Decision Trees and Random Forests
• Neural networks2
Unsupervised learning
In unsupervised learning, as you might guess, the training data is unlabeled
(Figure 1-7). The system tries to learn without a teacher.
Types of Machine Learning Systems 
| 
9


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0039_img_01.png)

<!-- Pagina 40 -->
Figure 1-7. An unlabeled training set for unsupervised learning
Here are some of the most important unsupervised learning algorithms (most of
these are covered in Chapters 8 and 9):
• Clustering
— K-Means
— DBSCAN
— Hierarchical Cluster Analysis (HCA)
• Anomaly detection and novelty detection
— One-class SVM
— Isolation Forest
• Visualization and dimensionality reduction
— Principal Component Analysis (PCA)
— Kernel PCA
— Locally Linear Embedding (LLE)
— t-Distributed Stochastic Neighbor Embedding (t-SNE)
• Association rule learning
— Apriori
— Eclat
For example, say you have a lot of data about your blog’s visitors. You may want to
run a clustering algorithm to try to detect groups of similar visitors (Figure 1-8). At
no point do you tell the algorithm which group a visitor belongs to: it finds those
connections without your help. For example, it might notice that 40% of your visitors
are males who love comic books and generally read your blog in the evening, while
20% are young sci-fi lovers who visit during the weekends. If you use a hierarchical
clustering algorithm, it may also subdivide each group into smaller groups. This may
help you target your posts for each group.
10 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0040_img_01.png)

<!-- Pagina 41 -->
3 Notice how animals are rather well separated from vehicles and how horses are close to deer but far from
birds. Figure reproduced with permission from Richard Socher et al., “Zero-Shot Learning Through Cross-
Modal Transfer,” Proceedings of the 26th International Conference on Neural Information Processing Systems 1
(2013): 935–943.
Figure 1-8. Clustering
Visualization algorithms are also good examples of unsupervised learning algorithms:
you feed them a lot of complex and unlabeled data, and they output a 2D or 3D rep‐
resentation of your data that can easily be plotted (Figure 1-9). These algorithms try
to preserve as much structure as they can (e.g., trying to keep separate clusters in the
input space from overlapping in the visualization) so that you can understand how
the data is organized and perhaps identify unsuspected patterns.
Figure 1-9. Example of a t-SNE visualization highlighting semantic clusters3
Types of Machine Learning Systems 
| 
11


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0041_img_01.png)

![Figura](images/page_0041_img_02.png)

<!-- Pagina 42 -->
A related task is dimensionality reduction, in which the goal is to simplify the data
without losing too much information. One way to do this is to merge several correla‐
ted features into one. For example, a car’s mileage may be strongly correlated with its
age, so the dimensionality reduction algorithm will merge them into one feature that
represents the car’s wear and tear. This is called feature extraction.
It is often a good idea to try to reduce the dimension of your train‐
ing data using a dimensionality reduction algorithm before you
feed it to another Machine Learning algorithm (such as a super‐
vised learning algorithm). It will run much faster, the data will take
up less disk and memory space, and in some cases it may also per‐
form better.
Yet another important unsupervised task is anomaly detection—for example, detect‐
ing unusual credit card transactions to prevent fraud, catching manufacturing defects,
or automatically removing outliers from a dataset before feeding it to another learn‐
ing algorithm. The system is shown mostly normal instances during training, so it
learns to recognize them; then, when it sees a new instance, it can tell whether it looks
like a normal one or whether it is likely an anomaly (see Figure 1-10). A very similar
task is novelty detection: it aims to detect new instances that look different from all
instances in the training set. This requires having a very “clean” training set, devoid of
any instance that you would like the algorithm to detect. For example, if you have
thousands of pictures of dogs, and 1% of these pictures represent Chihuahuas, then a
novelty detection algorithm should not treat new pictures of Chihuahuas as novelties.
On the other hand, anomaly detection algorithms may consider these dogs as so rare
and so different from other dogs that they would likely classify them as anomalies (no
offense to Chihuahuas).
Figure 1-10. Anomaly detection
Finally, another common unsupervised task is association rule learning, in which the
goal is to dig into large amounts of data and discover interesting relations between
12 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0042_img_01.png)

![Figura](images/page_0042_img_02.png)

<!-- Pagina 43 -->
4 That’s when the system works perfectly. In practice it often creates a few clusters per person, and sometimes
mixes up two people who look alike, so you may need to provide a few labels per person and manually clean
up some clusters.
attributes. For example, suppose you own a supermarket. Running an association rule
on your sales logs may reveal that people who purchase barbecue sauce and potato
chips also tend to buy steak. Thus, you may want to place these items close to one
another.
Semisupervised learning
Since labeling data is usually time-consuming and costly, you will often have plenty of
unlabeled instances, and few labeled instances. Some algorithms can deal with data
that’s partially labeled. This is called semisupervised learning (Figure 1-11).
Figure 1-11. Semisupervised learning with two classes (triangles and squares): the unla‐
beled examples (circles) help classify a new instance (the cross) into the triangle class
rather than the square class, even though it is closer to the labeled squares
Some photo-hosting services, such as Google Photos, are good examples of this. Once
you upload all your family photos to the service, it automatically recognizes that the
same person A shows up in photos 1, 5, and 11, while another person B shows up in
photos 2, 5, and 7. This is the unsupervised part of the algorithm (clustering). Now all
the system needs is for you to tell it who these people are. Just add one label per per‐
son4 and it is able to name everyone in every photo, which is useful for searching
photos.
Most semisupervised learning algorithms are combinations of unsupervised and
supervised algorithms. For example, deep belief networks (DBNs) are based on unsu‐
pervised components called restricted Boltzmann machines (RBMs) stacked on top of
one another. RBMs are trained sequentially in an unsupervised manner, and then the
whole system is fine-tuned using supervised learning techniques.
Types of Machine Learning Systems 
| 
13


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0043_img_01.png)

<!-- Pagina 44 -->
Reinforcement Learning
Reinforcement Learning is a very different beast. The learning system, called an agent
in this context, can observe the environment, select and perform actions, and get
rewards in return (or penalties in the form of negative rewards, as shown in
Figure 1-12). It must then learn by itself what is the best strategy, called a policy, to get
the most reward over time. A policy defines what action the agent should choose
when it is in a given situation.
Figure 1-12. Reinforcement Learning
For example, many robots implement Reinforcement Learning algorithms to learn
how to walk. DeepMind’s AlphaGo program is also a good example of Reinforcement
Learning: it made the headlines in May 2017 when it beat the world champion Ke Jie
at the game of Go. It learned its winning policy by analyzing millions of games, and
then playing many games against itself. Note that learning was turned off during the
games against the champion; AlphaGo was just applying the policy it had learned.
Batch and Online Learning
Another criterion used to classify Machine Learning systems is whether or not the
system can learn incrementally from a stream of incoming data.
14 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0044_img_01.png)

<!-- Pagina 45 -->
Batch learning
In batch learning, the system is incapable of learning incrementally: it must be trained
using all the available data. This will generally take a lot of time and computing
resources, so it is typically done offline. First the system is trained, and then it is
launched into production and runs without learning anymore; it just applies what it
has learned. This is called offline learning.
If you want a batch learning system to know about new data (such as a new type of
spam), you need to train a new version of the system from scratch on the full dataset
(not just the new data, but also the old data), then stop the old system and replace it
with the new one.
Fortunately, the whole process of training, evaluating, and launching a Machine
Learning system can be automated fairly easily (as shown in Figure 1-3), so even a
batch learning system can adapt to change. Simply update the data and train a new
version of the system from scratch as often as needed.
This solution is simple and often works fine, but training using the full set of data can
take many hours, so you would typically train a new system only every 24 hours or
even just weekly. If your system needs to adapt to rapidly changing data (e.g., to pre‐
dict stock prices), then you need a more reactive solution.
Also, training on the full set of data requires a lot of computing resources (CPU,
memory space, disk space, disk I/O, network I/O, etc.). If you have a lot of data and
you automate your system to train from scratch every day, it will end up costing you a
lot of money. If the amount of data is huge, it may even be impossible to use a batch
learning algorithm.
Finally, if your system needs to be able to learn autonomously and it has limited
resources (e.g., a smartphone application or a rover on Mars), then carrying around
large amounts of training data and taking up a lot of resources to train for hours
every day is a showstopper.
Fortunately, a better option in all these cases is to use algorithms that are capable of
learning incrementally.
Online learning
In online learning, you train the system incrementally by feeding it data instances
sequentially, either individually or in small groups called mini-batches. Each learning
step is fast and cheap, so the system can learn about new data on the fly, as it arrives
(see Figure 1-13).
Types of Machine Learning Systems 
| 
15

<!-- Pagina 46 -->
Figure 1-13. In online learning, a model is trained and launched into production, and
then it keeps learning as new data comes in
Online learning is great for systems that receive data as a continuous flow (e.g., stock
prices) and need to adapt to change rapidly or autonomously. It is also a good option
if you have limited computing resources: once an online learning system has learned
about new data instances, it does not need them anymore, so you can discard them
(unless you want to be able to roll back to a previous state and “replay” the data). This
can save a huge amount of space.
Online learning algorithms can also be used to train systems on huge datasets that
cannot fit in one machine’s main memory (this is called out-of-core learning). The
algorithm loads part of the data, runs a training step on that data, and repeats the
process until it has run on all of the data (see Figure 1-14).
Out-of-core learning is usually done offline (i.e., not on the live
system), so online learning can be a confusing name. Think of it as
incremental learning.
One important parameter of online learning systems is how fast they should adapt to
changing data: this is called the learning rate. If you set a high learning rate, then your
system will rapidly adapt to new data, but it will also tend to quickly forget the old
data (you don’t want a spam filter to flag only the latest kinds of spam it was shown).
Conversely, if you set a low learning rate, the system will have more inertia; that is, it
will learn more slowly, but it will also be less sensitive to noise in the new data or to
sequences of nonrepresentative data points (outliers).
16 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0046_img_01.png)

![Figura](images/page_0046_img_02.png)

<!-- Pagina 47 -->
Figure 1-14. Using online learning to handle huge datasets
A big challenge with online learning is that if bad data is fed to the system, the sys‐
tem’s performance will gradually decline. If it’s a live system, your clients will notice.
For example, bad data could come from a malfunctioning sensor on a robot, or from
someone spamming a search engine to try to rank high in search results. To reduce
this risk, you need to monitor your system closely and promptly switch learning off
(and possibly revert to a previously working state) if you detect a drop in perfor‐
mance. You may also want to monitor the input data and react to abnormal data (e.g.,
using an anomaly detection algorithm).
Instance-Based Versus Model-Based Learning
One more way to categorize Machine Learning systems is by how they generalize.
Most Machine Learning tasks are about making predictions. This means that given a
number of training examples, the system needs to be able to make good predictions
for (generalize to) examples it has never seen before. Having a good performance
measure on the training data is good, but insufficient; the true goal is to perform well
on new instances.
There are two main approaches to generalization: instance-based learning and
model-based learning.
Instance-based learning
Possibly the most trivial form of learning is simply to learn by heart. If you were to
create a spam filter this way, it would just flag all emails that are identical to emails
that have already been flagged by users—not the worst solution, but certainly not the
best.
Types of Machine Learning Systems 
| 
17


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0047_img_01.png)

<!-- Pagina 48 -->
Instead of just flagging emails that are identical to known spam emails, your spam
filter could be programmed to also flag emails that are very similar to known spam
emails. This requires a measure of similarity between two emails. A (very basic) simi‐
larity measure between two emails could be to count the number of words they have
in common. The system would flag an email as spam if it has many words in com‐
mon with a known spam email.
This is called instance-based learning: the system learns the examples by heart, then
generalizes to new cases by using a similarity measure to compare them to the
learned examples (or a subset of them). For example, in Figure 1-15 the new instance
would be classified as a triangle because the majority of the most similar instances
belong to that class.
Figure 1-15. Instance-based learning
Model-based learning
Another way to generalize from a set of examples is to build a model of these exam‐
ples and then use that model to make predictions. This is called model-based learning
(Figure 1-16).
Figure 1-16. Model-based learning
18 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0048_img_01.png)

![Figura](images/page_0048_img_02.png)

<!-- Pagina 49 -->
For example, suppose you want to know if money makes people happy, so you down‐
load the Better Life Index data from the OECD’s website and stats about gross domes‐
tic product (GDP) per capita from the IMF’s website. Then you join the tables and
sort by GDP per capita. Table 1-1 shows an excerpt of what you get.
Table 1-1. Does money make people happier?
Country
GDP per capita (USD)
Life satisfaction
Hungary
12,240
4.9
Korea
27,195
5.8
France
37,675
6.5
Australia
50,962
7.3
United States
55,805
7.2
Let’s plot the data for these countries (Figure 1-17).
Figure 1-17. Do you see a trend here?
There does seem to be a trend here! Although the data is noisy (i.e., partly random), it
looks like life satisfaction goes up more or less linearly as the country’s GDP per cap‐
ita increases. So you decide to model life satisfaction as a linear function of GDP per
capita. This step is called model selection: you selected a linear model of life satisfac‐
tion with just one attribute, GDP per capita (Equation 1-1).
Equation 1-1. A simple linear model
life_satisfaction = θ0 + θ1 × GDP_per_capita
Types of Machine Learning Systems 
| 
19


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0049_img_01.png)

<!-- Pagina 50 -->
5 By convention, the Greek letter θ (theta) is frequently used to represent model parameters.
This model has two model parameters, θ0 and θ1.5 By tweaking these parameters, you
can make your model represent any linear function, as shown in Figure 1-18.
Figure 1-18. A few possible linear models
Before you can use your model, you need to define the parameter values θ0 and θ1.
How can you know which values will make your model perform best? To answer this
question, you need to specify a performance measure. You can either define a utility
function (or fitness function) that measures how good your model is, or you can define
a cost function that measures how bad it is. For Linear Regression problems, people
typically use a cost function that measures the distance between the linear model’s
predictions and the training examples; the objective is to minimize this distance.
This is where the Linear Regression algorithm comes in: you feed it your training
examples, and it finds the parameters that make the linear model fit best to your data.
This is called training the model. In our case, the algorithm finds that the optimal
parameter values are θ0 = 4.85 and θ1 = 4.91 × 10–5.
Confusingly, the same word “model” can refer to a type of model
(e.g., Linear Regression), to a fully specified model architecture (e.g.,
Linear Regression with one input and one output), or to the final
trained model ready to be used for predictions (e.g., Linear Regres‐
sion with one input and one output, using θ0 = 4.85 and θ1 = 4.91 ×
10–5). Model selection consists in choosing the type of model and
fully specifying its architecture. Training a model means running
an algorithm to find the model parameters that will make it best fit
the training data (and hopefully make good predictions on new
data).
20 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0050_img_01.png)

![Figura](images/page_0050_img_02.png)

<!-- Pagina 51 -->
6 The prepare_country_stats() function’s definition is not shown here (see this chapter’s Jupyter notebook if
you want all the gory details). It’s just boring pandas code that joins the life satisfaction data from the OECD
with the GDP per capita data from the IMF.
7 It’s OK if you don’t understand all the code yet; we will present Scikit-Learn in the following chapters.
Now the model fits the training data as closely as possible (for a linear model), as you
can see in Figure 1-19.
Figure 1-19. The linear model that fits the training data best
You are finally ready to run the model to make predictions. For example, say you
want to know how happy Cypriots are, and the OECD data does not have the answer.
Fortunately, you can use your model to make a good prediction: you look up Cyprus’s
GDP per capita, find $22,587, and then apply your model and find that life satisfac‐
tion is likely to be somewhere around 4.85 + 22,587 × 4.91 × 10-5 = 5.96.
To whet your appetite, Example 1-1 shows the Python code that loads the data, pre‐
pares it,6 creates a scatterplot for visualization, and then trains a linear model and
makes a prediction.7
Example 1-1. Training and running a linear model using Scikit-Learn
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import sklearn.linear_model
# Load the data
oecd_bli = pd.read_csv("oecd_bli_2015.csv", thousands=',')
gdp_per_capita = pd.read_csv("gdp_per_capita.csv",thousands=',',delimiter='\t',
                             encoding='latin1', na_values="n/a")
Types of Machine Learning Systems 
| 
21


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0051_img_01.png)

<!-- Pagina 52 -->
# Prepare the data
country_stats = prepare_country_stats(oecd_bli, gdp_per_capita)
X = np.c_[country_stats["GDP per capita"]]
y = np.c_[country_stats["Life satisfaction"]]
# Visualize the data
country_stats.plot(kind='scatter', x="GDP per capita", y='Life satisfaction')
plt.show()
# Select a linear model
model = sklearn.linear_model.LinearRegression()
# Train the model
model.fit(X, y)
# Make a prediction for Cyprus
X_new = [[22587]]  # Cyprus's GDP per capita
print(model.predict(X_new)) # outputs [[ 5.96242338]]
If you had used an instance-based learning algorithm instead, you
would have found that Slovenia has the closest GDP per capita to
that of Cyprus ($20,732), and since the OECD data tells us that
Slovenians’ life satisfaction is 5.7, you would have predicted a life
satisfaction of 5.7 for Cyprus. If you zoom out a bit and look at the
two next-closest countries, you will find Portugal and Spain with
life satisfactions of 5.1 and 6.5, respectively. Averaging these three
values, you get 5.77, which is pretty close to your model-based pre‐
diction. This simple algorithm is called k-Nearest Neighbors regres‐
sion (in this example, k = 3).
Replacing the Linear Regression model with k-Nearest Neighbors
regression in the previous code is as simple as replacing these two
lines:
import sklearn.linear_model
model = sklearn.linear_model.LinearRegression()
with these two:
import sklearn.neighbors
model = sklearn.neighbors.KNeighborsRegressor(
    n_neighbors=3)
If all went well, your model will make good predictions. If not, you may need to use
more attributes (employment rate, health, air pollution, etc.), get more or better-
quality training data, or perhaps select a more powerful model (e.g., a Polynomial
Regression model).
22 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0052_img_01.png)

<!-- Pagina 53 -->
In summary:
• You studied the data.
• You selected a model.
• You trained it on the training data (i.e., the learning algorithm searched for the
model parameter values that minimize a cost function).
• Finally, you applied the model to make predictions on new cases (this is called
inference), hoping that this model will generalize well.
This is what a typical Machine Learning project looks like. In Chapter 2 you will
experience this firsthand by going through a project end to end.
We have covered a lot of ground so far: you now know what Machine Learning is
really about, why it is useful, what some of the most common categories of ML sys‐
tems are, and what a typical project workflow looks like. Now let’s look at what can go
wrong in learning and prevent you from making accurate predictions.
Main Challenges of Machine Learning
In short, since your main task is to select a learning algorithm and train it on some
data, the two things that can go wrong are “bad algorithm” and “bad data.” Let’s start
with examples of bad data.
Insufficient Quantity of Training Data
For a toddler to learn what an apple is, all it takes is for you to point to an apple and
say “apple” (possibly repeating this procedure a few times). Now the child is able to
recognize apples in all sorts of colors and shapes. Genius.
Machine Learning is not quite there yet; it takes a lot of data for most Machine Learn‐
ing algorithms to work properly. Even for very simple problems you typically need
thousands of examples, and for complex problems such as image or speech recogni‐
tion you may need millions of examples (unless you can reuse parts of an existing
model).
Main Challenges of Machine Learning 
| 
23

<!-- Pagina 54 -->
8 For example, knowing whether to write “to,” “two,” or “too,” depending on the context.
9 Figure reproduced with permission from Michele Banko and Eric Brill, “Scaling to Very Very Large Corpora
for Natural Language Disambiguation,” Proceedings of the 39th Annual Meeting of the Association for Compu‐
tational Linguistics (2001): 26–33.
10 Peter Norvig et al., “The Unreasonable Effectiveness of Data,” IEEE Intelligent Systems 24, no. 2 (2009): 8–12.
The Unreasonable Effectiveness of Data
In a famous paper published in 2001, Microsoft researchers Michele Banko and Eric
Brill showed that very different Machine Learning algorithms, including fairly simple
ones, performed almost identically well on a complex problem of natural language
disambiguation8 once they were given enough data (as you can see in Figure 1-20).
Figure 1-20. The importance of data versus algorithms9
As the authors put it, “these results suggest that we may want to reconsider the trade-
off between spending time and money on algorithm development versus spending it
on corpus development.”
The idea that data matters more than algorithms for complex problems was further
popularized by Peter Norvig et al. in a paper titled “The Unreasonable Effectiveness
of Data”, published in 2009.10 It should be noted, however, that small- and medium-
sized datasets are still very common, and it is not always easy or cheap to get extra
training data—so don’t abandon algorithms just yet.
24 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0054_img_01.png)

<!-- Pagina 55 -->
Nonrepresentative Training Data
In order to generalize well, it is crucial that your training data be representative of the
new cases you want to generalize to. This is true whether you use instance-based
learning or model-based learning.
For example, the set of countries we used earlier for training the linear model was not
perfectly representative; a few countries were missing. Figure 1-21 shows what the
data looks like when you add the missing countries.
Figure 1-21. A more representative training sample
If you train a linear model on this data, you get the solid line, while the old model is
represented by the dotted line. As you can see, not only does adding a few missing
countries significantly alter the model, but it makes it clear that such a simple linear
model is probably never going to work well. It seems that very rich countries are not
happier than moderately rich countries (in fact, they seem unhappier), and con‐
versely some poor countries seem happier than many rich countries.
By using a nonrepresentative training set, we trained a model that is unlikely to make
accurate predictions, especially for very poor and very rich countries.
It is crucial to use a training set that is representative of the cases you want to general‐
ize to. This is often harder than it sounds: if the sample is too small, you will have
sampling noise (i.e., nonrepresentative data as a result of chance), but even very large
samples can be nonrepresentative if the sampling method is flawed. This is called
sampling bias.
Main Challenges of Machine Learning 
| 
25


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0055_img_01.png)

<!-- Pagina 56 -->
Examples of Sampling Bias
Perhaps the most famous example of sampling bias happened during the US presi‐
dential election in 1936, which pitted Landon against Roosevelt: the Literary Digest
conducted a very large poll, sending mail to about 10 million people. It got 2.4 million
answers, and predicted with high confidence that Landon would get 57% of the votes.
Instead, Roosevelt won with 62% of the votes. The flaw was in the Literary Digest’s
sampling method:
• First, to obtain the addresses to send the polls to, the Literary Digest used tele‐
phone directories, lists of magazine subscribers, club membership lists, and the
like. All of these lists tended to favor wealthier people, who were more likely to
vote Republican (hence Landon).
• Second, less than 25% of the people who were polled answered. Again this intro‐
duced a sampling bias, by potentially ruling out people who didn’t care much
about politics, people who didn’t like the Literary Digest, and other key groups.
This is a special type of sampling bias called nonresponse bias.
Here is another example: say you want to build a system to recognize funk music vid‐
eos. One way to build your training set is to search for “funk music” on YouTube and
use the resulting videos. But this assumes that YouTube’s search engine returns a set of
videos that are representative of all the funk music videos on YouTube. In reality, the
search results are likely to be biased toward popular artists (and if you live in Brazil
you will get a lot of “funk carioca” videos, which sound nothing like James Brown).
On the other hand, how else can you get a large training set?
Poor-Quality Data
Obviously, if your training data is full of errors, outliers, and noise (e.g., due to poor-
quality measurements), it will make it harder for the system to detect the underlying
patterns, so your system is less likely to perform well. It is often well worth the effort
to spend time cleaning up your training data. The truth is, most data scientists spend
a significant part of their time doing just that. The following are a couple of examples
of when you’d want to clean up training data:
• If some instances are clearly outliers, it may help to simply discard them or try to
fix the errors manually.
• If some instances are missing a few features (e.g., 5% of your customers did not
specify their age), you must decide whether you want to ignore this attribute alto‐
gether, ignore these instances, fill in the missing values (e.g., with the median
age), or train one model with the feature and one model without it.
26 
| 
Chapter 1: The Machine Learning Landscape

<!-- Pagina 57 -->
Irrelevant Features
As the saying goes: garbage in, garbage out. Your system will only be capable of learn‐
ing if the training data contains enough relevant features and not too many irrelevant
ones. A critical part of the success of a Machine Learning project is coming up with a
good set of features to train on. This process, called feature engineering, involves the
following steps:
• Feature selection (selecting the most useful features to train on among existing
features)
• Feature extraction (combining existing features to produce a more useful one—as
we saw earlier, dimensionality reduction algorithms can help)
• Creating new features by gathering new data
Now that we have looked at many examples of bad data, let’s look at a couple of exam‐
ples of bad algorithms.
Overfitting the Training Data
Say you are visiting a foreign country and the taxi driver rips you off. You might be
tempted to say that all taxi drivers in that country are thieves. Overgeneralizing is
something that we humans do all too often, and unfortunately machines can fall into
the same trap if we are not careful. In Machine Learning this is called overfitting: it
means that the model performs well on the training data, but it does not generalize
well.
Figure 1-22 shows an example of a high-degree polynomial life satisfaction model
that strongly overfits the training data. Even though it performs much better on the
training data than the simple linear model, would you really trust its predictions?
Figure 1-22. Overfitting the training data
Main Challenges of Machine Learning 
| 
27


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0057_img_01.png)

<!-- Pagina 58 -->
Complex models such as deep neural networks can detect subtle patterns in the data,
but if the training set is noisy, or if it is too small (which introduces sampling noise),
then the model is likely to detect patterns in the noise itself. Obviously these patterns
will not generalize to new instances. For example, say you feed your life satisfaction
model many more attributes, including uninformative ones such as the country’s
name. In that case, a complex model may detect patterns like the fact that all coun‐
tries in the training data with a w in their name have a life satisfaction greater than 7:
New Zealand (7.3), Norway (7.4), Sweden (7.2), and Switzerland (7.5). How confident
are you that the w-satisfaction rule generalizes to Rwanda or Zimbabwe? Obviously
this pattern occurred in the training data by pure chance, but the model has no way
to tell whether a pattern is real or simply the result of noise in the data.
Overfitting happens when the model is too complex relative to the
amount and noisiness of the training data. Here are possible solu‐
tions:
• Simplify the model by selecting one with fewer parameters
(e.g., a linear model rather than a high-degree polynomial
model), by reducing the number of attributes in the training
data, or by constraining the model.
• Gather more training data.
• Reduce the noise in the training data (e.g., fix data errors and
remove outliers).
Constraining a model to make it simpler and reduce the risk of overfitting is called
regularization. For example, the linear model we defined earlier has two parameters,
θ0 and θ1. This gives the learning algorithm two degrees of freedom to adapt the model
to the training data: it can tweak both the height (θ0) and the slope (θ1) of the line. If
we forced θ1 = 0, the algorithm would have only one degree of freedom and would
have a much harder time fitting the data properly: all it could do is move the line up
or down to get as close as possible to the training instances, so it would end up
around the mean. A very simple model indeed! If we allow the algorithm to modify θ1
but we force it to keep it small, then the learning algorithm will effectively have some‐
where in between one and two degrees of freedom. It will produce a model that’s sim‐
pler than one with two degrees of freedom, but more complex than one with just one.
You want to find the right balance between fitting the training data perfectly and
keeping the model simple enough to ensure that it will generalize well.
Figure 1-23 shows three models. The dotted line represents the original model that
was trained on the countries represented as circles (without the countries represented
as squares), the dashed line is our second model trained with all countries (circles and
squares), and the solid line is a model trained with the same data as the first model
28 
| 
Chapter 1: The Machine Learning Landscape


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0058_img_01.png)

<!-- Pagina 59 -->
but with a regularization constraint. You can see that regularization forced the model
to have a smaller slope: this model does not fit the training data (circles) as well as the
first model, but it actually generalizes better to new examples that it did not see dur‐
ing training (squares).
Figure 1-23. Regularization reduces the risk of overfitting
The amount of regularization to apply during learning can be controlled by a hyper‐
parameter. A hyperparameter is a parameter of a learning algorithm (not of the
model). As such, it is not affected by the learning algorithm itself; it must be set prior
to training and remains constant during training. If you set the regularization hyper‐
parameter to a very large value, you will get an almost flat model (a slope close to
zero); the learning algorithm will almost certainly not overfit the training data, but it
will be less likely to find a good solution. Tuning hyperparameters is an important
part of building a Machine Learning system (you will see a detailed example in the
next chapter).
Underfitting the Training Data
As you might guess, underfitting is the opposite of overfitting: it occurs when your
model is too simple to learn the underlying structure of the data. For example, a lin‐
ear model of life satisfaction is prone to underfit; reality is just more complex than
the model, so its predictions are bound to be inaccurate, even on the training
examples.
Here are the main options for fixing this problem:
• Select a more powerful model, with more parameters.
• Feed better features to the learning algorithm (feature engineering).
• Reduce the constraints on the model (e.g., reduce the regularization hyperpara‐
meter).
Main Challenges of Machine Learning 
| 
29


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0059_img_01.png)

<!-- Pagina 60 -->
Stepping Back
By now you know a lot about Machine Learning. However, we went through so many
concepts that you may be feeling a little lost, so let’s step back and look at the big
picture:
• Machine Learning is about making machines get better at some task by learning
from data, instead of having to explicitly code rules.
• There are many different types of ML systems: supervised or not, batch or online,
instance-based or model-based.
• In an ML project you gather data in a training set, and you feed the training set to
a learning algorithm. If the algorithm is model-based, it tunes some parameters
to fit the model to the training set (i.e., to make good predictions on the training
set itself), and then hopefully it will be able to make good predictions on new
cases as well. If the algorithm is instance-based, it just learns the examples by
heart and generalizes to new instances by using a similarity measure to compare
them to the learned instances.
• The system will not perform well if your training set is too small, or if the data is
not representative, is noisy, or is polluted with irrelevant features (garbage in,
garbage out). Lastly, your model needs to be neither too simple (in which case it
will underfit) nor too complex (in which case it will overfit).
There’s just one last important topic to cover: once you have trained a model, you
don’t want to just “hope” it generalizes to new cases. You want to evaluate it and fine-
tune it if necessary. Let’s see how to do that.
Testing and Validating
The only way to know how well a model will generalize to new cases is to actually try
it out on new cases. One way to do that is to put your model in production and moni‐
tor how well it performs. This works well, but if your model is horribly bad, your
users will complain—not the best idea.
A better option is to split your data into two sets: the training set and the test set. As
these names imply, you train your model using the training set, and you test it using
the test set. The error rate on new cases is called the generalization error (or out-of-
sample error), and by evaluating your model on the test set, you get an estimate of this
error. This value tells you how well your model will perform on instances it has never
seen before.
If the training error is low (i.e., your model makes few mistakes on the training set)
but the generalization error is high, it means that your model is overfitting the train‐
ing data.
30 
| 
Chapter 1: The Machine Learning Landscape

<!-- Pagina 61 -->
It is common to use 80% of the data for training and hold out 20%
for testing. However, this depends on the size of the dataset: if it
contains 10 million instances, then holding out 1% means your test
set will contain 100,000 instances, probably more than enough to
get a good estimate of the generalization error.
Hyperparameter Tuning and Model Selection
Evaluating a model is simple enough: just use a test set. But suppose you are hesitat‐
ing between two types of models (say, a linear model and a polynomial model): how
can you decide between them? One option is to train both and compare how well
they generalize using the test set.
Now suppose that the linear model generalizes better, but you want to apply some
regularization to avoid overfitting. The question is, how do you choose the value of
the regularization hyperparameter? One option is to train 100 different models using
100 different values for this hyperparameter. Suppose you find the best hyperparame‐
ter value that produces a model with the lowest generalization error—say, just 5%
error. You launch this model into production, but unfortunately it does not perform
as well as expected and produces 15% errors. What just happened?
The problem is that you measured the generalization error multiple times on the test
set, and you adapted the model and hyperparameters to produce the best model for
that particular set. This means that the model is unlikely to perform as well on new
data.
A common solution to this problem is called holdout validation: you simply hold out
part of the training set to evaluate several candidate models and select the best one.
The new held-out set is called the validation set (or sometimes the development set, or
dev set). More specifically, you train multiple models with various hyperparameters
on the reduced training set (i.e., the full training set minus the validation set), and
you select the model that performs best on the validation set. After this holdout vali‐
dation process, you train the best model on the full training set (including the valida‐
tion set), and this gives you the final model. Lastly, you evaluate this final model on
the test set to get an estimate of the generalization error.
This solution usually works quite well. However, if the validation set is too small, then
model evaluations will be imprecise: you may end up selecting a suboptimal model by
mistake. Conversely, if the validation set is too large, then the remaining training set
will be much smaller than the full training set. Why is this bad? Well, since the final
model will be trained on the full training set, it is not ideal to compare candidate
models trained on a much smaller training set. It would be like selecting the fastest
sprinter to participate in a marathon. One way to solve this problem is to perform
repeated cross-validation, using many small validation sets. Each model is evaluated
once per validation set after it is trained on the rest of the data. By averaging out all
Testing and Validating 
| 
31


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0061_img_01.png)

<!-- Pagina 62 -->
the evaluations of a model, you get a much more accurate measure of its perfor‐
mance. There is a drawback, however: the training time is multiplied by the number
of validation sets.
Data Mismatch
In some cases, it’s easy to get a large amount of data for training, but this data proba‐
bly won’t be perfectly representative of the data that will be used in production. For
example, suppose you want to create a mobile app to take pictures of flowers and
automatically determine their species. You can easily download millions of pictures of
flowers on the web, but they won’t be perfectly representative of the pictures that will
actually be taken using the app on a mobile device. Perhaps you only have 10,000 rep‐
resentative pictures (i.e., actually taken with the app). In this case, the most important
rule to remember is that the validation set and the test set must be as representative as
possible of the data you expect to use in production, so they should be composed
exclusively of representative pictures: you can shuffle them and put half in the valida‐
tion set and half in the test set (making sure that no duplicates or near-duplicates end
up in both sets). But after training your model on the web pictures, if you observe
that the performance of the model on the validation set is disappointing, you will not
know whether this is because your model has overfit the training set, or whether this
is just due to the mismatch between the web pictures and the mobile app pictures.
One solution is to hold out some of the training pictures (from the web) in yet
another set that Andrew Ng calls the train-dev set. After the model is trained (on the
training set, not on the train-dev set), you can evaluate it on the train-dev set. If it
performs well, then the model is not overfitting the training set. If it performs poorly
on the validation set, the problem must be coming from the data mismatch. You can
try to tackle this problem by preprocessing the web images to make them look more
like the pictures that will be taken by the mobile app, and then retraining the model.
Conversely, if the model performs poorly on the train-dev set, then it must have over‐
fit the training set, so you should try to simplify or regularize the model, get more
training data, and clean up the training data.
32 
| 
Chapter 1: The Machine Learning Landscape

<!-- Pagina 63 -->
11 David Wolpert, “The Lack of A Priori Distinctions Between Learning Algorithms,” Neural Computation 8, no.
7 (1996): 1341–1390.
No Free Lunch Theorem
A model is a simplified version of the observations. The simplifications are meant to
discard the superfluous details that are unlikely to generalize to new instances. To
decide what data to discard and what data to keep, you must make assumptions. For
example, a linear model makes the assumption that the data is fundamentally linear
and that the distance between the instances and the straight line is just noise, which
can safely be ignored.
In a famous 1996 paper,11 David Wolpert demonstrated that if you make absolutely
no assumption about the data, then there is no reason to prefer one model over any
other. This is called the No Free Lunch (NFL) theorem. For some datasets the best
model is a linear model, while for other datasets it is a neural network. There is no
model that is a priori guaranteed to work better (hence the name of the theorem). The
only way to know for sure which model is best is to evaluate them all. Since this is not
possible, in practice you make some reasonable assumptions about the data and eval‐
uate only a few reasonable models. For example, for simple tasks you may evaluate
linear models with various levels of regularization, and for a complex problem you
may evaluate various neural networks.
Exercises
In this chapter we have covered some of the most important concepts in Machine
Learning. In the next chapters we will dive deeper and write more code, but before we
do, make sure you know how to answer the following questions:
1. How would you define Machine Learning?
2. Can you name four types of problems where it shines?
3. What is a labeled training set?
4. What are the two most common supervised tasks?
5. Can you name four common unsupervised tasks?
6. What type of Machine Learning algorithm would you use to allow a robot to
walk in various unknown terrains?
7. What type of algorithm would you use to segment your customers into multiple
groups?
8. Would you frame the problem of spam detection as a supervised learning prob‐
lem or an unsupervised learning problem?
Exercises 
| 
33

<!-- Pagina 64 -->
9. What is an online learning system?
10. What is out-of-core learning?
11. What type of learning algorithm relies on a similarity measure to make predic‐
tions?
12. What is the difference between a model parameter and a learning algorithm’s
hyperparameter?
13. What do model-based learning algorithms search for? What is the most common
strategy they use to succeed? How do they make predictions?
14. Can you name four of the main challenges in Machine Learning?
15. If your model performs great on the training data but generalizes poorly to new
instances, what is happening? Can you name three possible solutions?
16. What is a test set, and why would you want to use it?
17. What is the purpose of a validation set?
18. What is the train-dev set, when do you need it, and how do you use it?
19. What can go wrong if you tune hyperparameters using the test set?
Solutions to these exercises are available in Appendix A.
34 
| 
Chapter 1: The Machine Learning Landscape

<!-- Pagina 65 -->
1 The example project is fictitious; the goal is to illustrate the main steps of a Machine Learning project, not to
learn anything about the real estate business.
CHAPTER 2
End-to-End Machine Learning Project
In this chapter you will work through an example project end to end, pretending to
be a recently hired data scientist at a real estate company.1 Here are the main steps
you will go through:
1. Look at the big picture.
2. Get the data.
3. Discover and visualize the data to gain insights.
4. Prepare the data for Machine Learning algorithms.
5. Select a model and train it.
6. Fine-tune your model.
7. Present your solution.
8. Launch, monitor, and maintain your system.
Working with Real Data
When you are learning about Machine Learning, it is best to experiment with real-
world data, not artificial datasets. Fortunately, there are thousands of open datasets to
choose from, ranging across all sorts of domains. Here are a few places you can look
to get data:
35

<!-- Pagina 66 -->
2 The original dataset appeared in R. Kelley Pace and Ronald Barry, “Sparse Spatial Autoregressions,” Statistics
& Probability Letters 33, no. 3 (1997): 291–297.
• Popular open data repositories
— UC Irvine Machine Learning Repository
— Kaggle datasets
— Amazon’s AWS datasets
• Meta portals (they list open data repositories)
— Data Portals
— OpenDataMonitor
— Quandl
• Other pages listing many popular open data repositories
— Wikipedia’s list of Machine Learning datasets
— Quora.com
— The datasets subreddit
In this chapter we’ll use the California Housing Prices dataset from the StatLib repos‐
itory2 (see Figure 2-1). This dataset is based on data from the 1990 California census.
It is not exactly recent (a nice house in the Bay Area was still affordable at the time),
but it has many qualities for learning, so we will pretend it is recent data. For teaching
purposes I’ve added a categorical attribute and removed a few features.
Figure 2-1. California housing prices
36 
| 
Chapter 2: End-to-End Machine Learning Project


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0066_img_01.png)

<!-- Pagina 67 -->
3 A piece of information fed to a Machine Learning system is often called a signal, in reference to Claude Shan‐
non’s information theory, which he developed at Bell Labs to improve telecommunications. His theory: you
want a high signal-to-noise ratio.
Look at the Big Picture
Welcome to the Machine Learning Housing Corporation! Your first task is to use Cal‐
ifornia census data to build a model of housing prices in the state. This data includes
metrics such as the population, median income, and median housing price for each
block group in California. Block groups are the smallest geographical unit for which
the US Census Bureau publishes sample data (a block group typically has a popula‐
tion of 600 to 3,000 people). We will call them “districts” for short.
Your model should learn from this data and be able to predict the median housing
price in any district, given all the other metrics.
Since you are a well-organized data scientist, the first thing you
should do is pull out your Machine Learning project checklist. You
can start with the one in Appendix B; it should work reasonably
well for most Machine Learning projects, but make sure to adapt it
to your needs. In this chapter we will go through many checklist
items, but we will also skip a few, either because they are self-
explanatory or because they will be discussed in later chapters.
Frame the Problem
The first question to ask your boss is what exactly the business objective is. Building a
model is probably not the end goal. How does the company expect to use and benefit
from this model? Knowing the objective is important because it will determine how
you frame the problem, which algorithms you will select, which performance meas‐
ure you will use to evaluate your model, and how much effort you will spend tweak‐
ing it.
Your boss answers that your model’s output (a prediction of a district’s median hous‐
ing price) will be fed to another Machine Learning system (see Figure 2-2), along
with many other signals.3 This downstream system will determine whether it is worth
investing in a given area or not. Getting this right is critical, as it directly affects
revenue.
Look at the Big Picture 
| 
37


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0067_img_01.png)

<!-- Pagina 68 -->
Figure 2-2. A Machine Learning pipeline for real estate investments
Pipelines
A sequence of data processing components is called a data pipeline. Pipelines are very
common in Machine Learning systems, since there is a lot of data to manipulate and
many data transformations to apply.
Components typically run asynchronously. Each component pulls in a large amount
of data, processes it, and spits out the result in another data store. Then, some time
later, the next component in the pipeline pulls this data and spits out its own output.
Each component is fairly self-contained: the interface between components is simply
the data store. This makes the system simple to grasp (with the help of a data flow
graph), and different teams can focus on different components. Moreover, if a com‐
ponent breaks down, the downstream components can often continue to run nor‐
mally (at least for a while) by just using the last output from the broken component.
This makes the architecture quite robust.
On the other hand, a broken component can go unnoticed for some time if proper
monitoring is not implemented. The data gets stale and the overall system’s perfor‐
mance drops.
The next question to ask your boss is what the current solution looks like (if any).
The current situation will often give you a reference for performance, as well as
insights on how to solve the problem. Your boss answers that the district housing pri‐
ces are currently estimated manually by experts: a team gathers up-to-date informa‐
tion about a district, and when they cannot get the median housing price, they
estimate it using complex rules.
This is costly and time-consuming, and their estimates are not great; in cases where
they manage to find out the actual median housing price, they often realize that their
estimates were off by more than 20%. This is why the company thinks that it would
be useful to train a model to predict a district’s median housing price, given other
38 
| 
Chapter 2: End-to-End Machine Learning Project


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0068_img_01.png)

<!-- Pagina 69 -->

> [Error procesando con Ollama: [WinError 10061] No se puede establecer una conexión ya que el equipo de destino denegó expresamente dicha conexión]

data about that district. The census data looks like a great dataset to exploit for this
purpose, since it includes the median housing prices of thousands of districts, as well
as other data.
With all this information, you are now ready to start designing your system. First,
you need to frame the problem: is it supervised, unsupervised, or Reinforcement
Learning? Is it a classification task, a regression task, or something else? Should you
use batch learning or online learning techniques? Before you read on, pause and try
to answer these questions for yourself.
Have you found the answers? Let’s see: it is clearly a typical supervised learning task,
since you are given labeled training examples (each instance comes with the expected
output, i.e., the district’s median housing price). It is also a typical regression task,
since you are asked to predict a value. More specifically, this is a multiple regression
problem, since the system will use multiple features to make a prediction (it will use
the district’s population, the median income, etc.). It is also a univariate regression
problem, since we are only trying to predict a single value for each district. If we were
trying to predict multiple values per district, it would be a multivariate regression
problem. Finally, there is no continuous flow of data coming into the system, there is
no particular need to adjust to changing data rapidly, and the data is small enough to
fit in memory, so plain batch learning should do just fine.
If the data were huge, you could either split your batch learning
work across multiple servers (using the MapReduce technique) or
use an online learning technique.
Select a Performance Measure
Your next step is to select a performance measure. A typical performance measure for
regression problems is the Root Mean Square Error (RMSE). It gives an idea of how
much error the system typically makes in its predictions, with a higher weight for
large errors. Equation 2-1 shows the mathematical formula to compute the RMSE.
Equation 2-1. Root Mean Square Error (RMSE)
RMSE X, h =
1
m ∑
i = 1
m
h x i
−y i 2
Look at the Big Picture 
| 
39


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0069_img_01.png)


<!-- Pagina 70 -->
4 Recall that the transpose operator flips a column vector into a row vector (and vice versa).
Notations
This equation introduces several very common Machine Learning notations that we
will use throughout this book:
• m is the number of instances in the dataset you are measuring the RMSE on.
— For example, if you are evaluating the RMSE on a validation set of 2,000 dis‐
tricts, then m = 2,000.
• x(i) is a vector of all the feature values (excluding the label) of the ith instance in
the dataset, and y(i) is its label (the desired output value for that instance).
— For example, if the first district in the dataset is located at longitude –118.29°,
latitude 33.91°, and it has 1,416 inhabitants with a median income of $38,372,
and the median house value is $156,400 (ignoring the other features for now),
then:
x 1 =
−118.29
33.91
1,416
38,372
and:
y 1 = 156,400
• X is a matrix containing all the feature values (excluding labels) of all instances in
the dataset. There is one row per instance, and the ith row is equal to the trans‐
pose of x(i), noted (x(i))⊺.4
— For example, if the first district is as just described, then the matrix X looks
like this:
X =
x 1 ⊺
x 2 ⊺
⋮
x 1999 ⊺
x 2000 ⊺
= −118.29 33.91 1,416 38,372
⋮
⋮
⋮
⋮
40 
| 
Chapter 2: End-to-End Machine Learning Project

<!-- Pagina 71 -->

> [Error procesando con Ollama: [WinError 10061] No se puede establecer una conexión ya que el equipo de destino denegó expresamente dicha conexión]

• h is your system’s prediction function, also called a hypothesis. When your system
is given an instance’s feature vector x(i), it outputs a predicted value ŷ(i) = h(x(i))
for that instance (ŷ is pronounced “y-hat”).
— For example, if your system predicts that the median housing price in the first
district is $158,400, then ŷ(1) = h(x(1)) = 158,400. The prediction error for this
district is ŷ(1) – y(1) = 2,000.
• RMSE(X,h) is the cost function measured on the set of examples using your
hypothesis h.
We use lowercase italic font for scalar values (such as m or y(i)) and function names
(such as h), lowercase bold font for vectors (such as x(i)), and uppercase bold font for
matrices (such as X).
Even though the RMSE is generally the preferred performance measure for regression
tasks, in some contexts you may prefer to use another function. For example, suppose
that there are many outlier districts. In that case, you may consider using the mean
absolute error (MAE, also called the average absolute deviation; see Equation 2-2):
Equation 2-2. Mean absolute error (MAE)
MAE X, h = 1
m ∑
i = 1
m
h x i
−y i
Both the RMSE and the MAE are ways to measure the distance between two vectors:
the vector of predictions and the vector of target values. Various distance measures,
or norms, are possible:
• Computing the root of a sum of squares (RMSE) corresponds to the Euclidean
norm: this is the notion of distance you are familiar with. It is also called the ℓ2
norm, noted ∥ · ∥2 (or just ∥ · ∥).
• Computing the sum of absolutes (MAE) corresponds to the ℓ1 norm, noted ∥ · ∥1.
This is sometimes called the Manhattan norm because it measures the distance
between two points in a city if you can only travel along orthogonal city blocks.
• More generally, the ℓk norm of a vector v containing n elements is defined as ∥v∥k
= (|v0|k + |v1|k + ... + |vn|k)1/k. ℓ0 gives the number of nonzero elements in the vec‐
tor, and ℓ∞ gives the maximum absolute value in the vector.
• The higher the norm index, the more it focuses on large values and neglects small
ones. This is why the RMSE is more sensitive to outliers than the MAE. But when
outliers are exponentially rare (like in a bell-shaped curve), the RMSE performs
very well and is generally preferred.
Look at the Big Picture 
| 
41


<!-- Pagina 72 -->
5 The latest version of Python 3 is recommended. Python 2.7+ may work too, but now that it’s deprecated, all
major scientific libraries are dropping support for it, so you should migrate to Python 3 as soon as possible.
Check the Assumptions
Lastly, it is good practice to list and verify the assumptions that have been made so far
(by you or others); this can help you catch serious issues early on. For example, the
district prices that your system outputs are going to be fed into a downstream
Machine Learning system, and you assume that these prices are going to be used as
such. But what if the downstream system converts the prices into categories (e.g.,
“cheap,” “medium,” or “expensive”) and then uses those categories instead of the pri‐
ces themselves? In this case, getting the price perfectly right is not important at all;
your system just needs to get the category right. If that’s so, then the problem should
have been framed as a classification task, not a regression task. You don’t want to find
this out after working on a regression system for months.
Fortunately, after talking with the team in charge of the downstream system, you are
confident that they do indeed need the actual prices, not just categories. Great! You’re
all set, the lights are green, and you can start coding now!
Get the Data
It’s time to get your hands dirty. Don’t hesitate to pick up your laptop and walk
through the following code examples in a Jupyter notebook. The full Jupyter note‐
book is available at https://github.com/ageron/handson-ml2.
Create the Workspace
First you will need to have Python installed. It is probably already installed on your
system. If not, you can get it at https://www.python.org/.5
Next you need to create a workspace directory for your Machine Learning code and
datasets. Open a terminal and type the following commands (after the $ prompts):
$ export ML_PATH="$HOME/ml"      # You can change the path if you prefer
$ mkdir -p $ML_PATH
You will need a number of Python modules: Jupyter, NumPy, pandas, Matplotlib, and
Scikit-Learn. If you already have Jupyter running with all these modules installed,
you can safely skip to “Download the Data” on page 46. If you don’t have them yet,
there are many ways to install them (and their dependencies). You can use your
system’s packaging system (e.g., apt-get on Ubuntu, or MacPorts or Homebrew on
macOS), install a Scientific Python distribution such as Anaconda and use its packag‐
ing system, or just use Python’s own packaging system, pip, which is included by
42 
| 
Chapter 2: End-to-End Machine Learning Project

<!-- Pagina 73 -->
6 I’ll show the installation steps using pip in a bash shell on a Linux or macOS system. You may need to adapt
these commands to your own system. On Windows, I recommend installing Anaconda instead.
7 If you want to upgrade pip for all users on your machine rather than just your own user, you should remove
the --user option and make sure you have administrator rights (e.g., by adding sudo before the whole com‐
mand on Linux or macOS).
8 Alternative tools include venv (very similar to virtualenv and included in the standard library), virtualenv‐
wrapper (provides extra functionalities on top of virtualenv), pyenv (allows easy switching between Python
versions), and pipenv (a great packaging tool by the same author as the popular requests library, built on top
of pip and virtualenv).
default with the Python binary installers (since Python 2.7.9).6 You can check to see if
pip is installed by typing the following command:
$ python3 -m pip --version
pip 19.3.1 from [...]/lib/python3.7/site-packages/pip (python 3.7)
You should make sure you have a recent version of pip installed. To upgrade the pip
module, type the following (the exact version may differ):7
$ python3 -m pip install --user -U pip
Collecting pip
[...]
Successfully installed pip-19.3.1
Creating an Isolated Environment
If you would like to work in an isolated environment (which is strongly recom‐
mended so that you can work on different projects without having conflicting library
versions), install virtualenv8 by running the following pip command (again, if you
want virtualenv to be installed for all users on your machine, remove --user and run
this command with administrator rights):
$ python3 -m pip install --user -U virtualenv
Collecting virtualenv
[...]
Successfully installed virtualenv-16.7.6
Now you can create an isolated Python environment by typing this:
$ cd $ML_PATH
$ python3 -m virtualenv my_env
Using base prefix '[...]'
New python executable in [...]/ml/my_env/bin/python3
Also creating executable in [...]/ml/my_env/bin/python
Installing setuptools, pip, wheel...done.
Now every time you want to activate this environment, just open a terminal and type
the following:
Get the Data 
| 
43

<!-- Pagina 74 -->
9 Note that Jupyter can handle multiple versions of Python, and even many other languages such as R or
Octave.
$ cd $ML_PATH
$ source my_env/bin/activate # on Linux or macOS
$ .\my_env\Scripts\activate  # on Windows
To deactivate this environment, type deactivate. While the environment is active,
any package you install using pip will be installed in this isolated environment, and
Python will only have access to these packages (if you also want access to the system’s
packages, you should create the environment using virtualenv’s --system-site-
packages option). Check out virtualenv’s documentation for more information.
Now you can install all the required modules and their dependencies using this sim‐
ple pip command (if you are not using a virtualenv, you will need the --user option
or administrator rights):
$ python3 -m pip install -U jupyter matplotlib numpy pandas scipy scikit-learn
Collecting jupyter
  Downloading https://[...]/jupyter-1.0.0-py2.py3-none-any.whl
Collecting matplotlib
  [...]
If you created a virtualenv, you need to register it to Jupyter and give it a name:
$ python3 -m ipykernel install --user --name=python3
Now you can fire up Jupyter by typing the following command:
$ jupyter notebook
[...] Serving notebooks from local directory: [...]/ml
[...] The Jupyter Notebook is running at:
[...] http://localhost:8888/?token=60995e108e44ac8d8865a[...]
[...]  or http://127.0.0.1:8889/?token=60995e108e44ac8d8865a[...]
[...] Use Control-C to stop this server and shut down all kernels [...]
A Jupyter server is now running in your terminal, listening to port 8888. You can visit
this server by opening your web browser to http://localhost:8888/ (this usually hap‐
pens automatically when the server starts). You should see your empty workspace
directory (containing only the env directory if you followed the preceding virtualenv
instructions).
Now create a new Python notebook by clicking the New button and selecting the
appropriate Python version9 (see Figure 2-3). Doing that will create a new notebook
file called Untitled.ipynb in your workspace, start a Jupyter Python kernel to run the
notebook, and open this notebook in a new tab. You should start by renaming this
notebook to “Housing” (this will automatically rename the file to Housing.ipynb) by
clicking Untitled and typing the new name.
44 
| 
Chapter 2: End-to-End Machine Learning Project

<!-- Pagina 75 -->
Figure 2-3. Your workspace in Jupyter
A notebook contains a list of cells. Each cell can contain executable code or formatted
text. Right now the notebook contains only one empty code cell, labeled “In [1]:”. Try
typing print("Hello world!") in the cell and clicking the play button (see
Figure 2-4) or pressing Shift-Enter. This sends the current cell to this notebook’s
Python kernel, which runs it and returns the output. The result is displayed below the
cell, and since you’ve reached the end of the notebook, a new cell is automatically cre‐
ated. Go through the User Interface Tour from Jupyter’s Help menu to learn the
basics.
Figure 2-4. Hello world Python notebook
Get the Data 
| 
45


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0075_img_01.png)

![Figura](images/page_0075_img_02.png)

<!-- Pagina 76 -->
10 You might also need to check legal constraints, such as private fields that should never be copied to unsafe
data stores.
11 In a real project you would save this code in a Python file, but for now you can just write it in your Jupyter
notebook.
Download the Data
In typical environments your data would be available in a relational database (or
some other common data store) and spread across multiple tables/documents/files.
To access it, you would first need to get your credentials and access authorizations10
and familiarize yourself with the data schema. In this project, however, things are
much simpler: you will just download a single compressed file, housing.tgz, which
contains a comma-separated values (CSV) file called housing.csv with all the data.
You could use your web browser to download the file and run tar xzf housing.tgz
to decompress it and extract the CSV file, but it is preferable to create a small func‐
tion to do that. Having a function that downloads the data is useful in particular if the
data changes regularly: you can write a small script that uses the function to fetch the
latest data (or you can set up a scheduled job to do that automatically at regular inter‐
vals). Automating the process of fetching the data is also useful if you need to install
the dataset on multiple machines.
Here is the function to fetch the data:11
import os
import tarfile
import urllib
DOWNLOAD_ROOT = "https://raw.githubusercontent.com/ageron/handson-ml2/master/"
HOUSING_PATH = os.path.join("datasets", "housing")
HOUSING_URL = DOWNLOAD_ROOT + "datasets/housing/housing.tgz"
def fetch_housing_data(housing_url=HOUSING_URL, housing_path=HOUSING_PATH):
    os.makedirs(housing_path, exist_ok=True)
    tgz_path = os.path.join(housing_path, "housing.tgz")
    urllib.request.urlretrieve(housing_url, tgz_path)
    housing_tgz = tarfile.open(tgz_path)
    housing_tgz.extractall(path=housing_path)
    housing_tgz.close()
Now when you call fetch_housing_data(), it creates a datasets/housing directory in
your workspace, downloads the housing.tgz file, and extracts the housing.csv file from
it in this directory.
46 
| 
Chapter 2: End-to-End Machine Learning Project

<!-- Pagina 77 -->
Now let’s load the data using pandas. Once again, you should write a small function
to load the data:
import pandas as pd
def load_housing_data(housing_path=HOUSING_PATH):
    csv_path = os.path.join(housing_path, "housing.csv")
    return pd.read_csv(csv_path)
This function returns a pandas DataFrame object containing all the data.
Take a Quick Look at the Data Structure
Let’s take a look at the top five rows using the DataFrame’s head() method (see
Figure 2-5).
Figure 2-5. Top five rows in the dataset
Each row represents one district. There are 10 attributes (you can see the first 6 in the
screenshot): longitude, latitude, housing_median_age, total_rooms, total_bed
rooms, 
population, 
households, 
median_income, 
median_house_value, and
ocean_proximity.
The info() method is useful to get a quick description of the data, in particular the
total number of rows, each attribute’s type, and the number of nonnull values (see
Figure 2-6).
Get the Data 
| 
47


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0077_img_01.png)

<!-- Pagina 78 -->
Figure 2-6. Housing info
There are 20,640 instances in the dataset, which means that it is fairly small by
Machine Learning standards, but it’s perfect to get started. Notice that the total_bed
rooms attribute has only 20,433 nonnull values, meaning that 207 districts are missing
this feature. We will need to take care of this later.
All attributes are numerical, except the ocean_proximity field. Its type is object, so it
could hold any kind of Python object. But since you loaded this data from a CSV file,
you know that it must be a text attribute. When you looked at the top five rows, you
probably noticed that the values in the ocean_proximity column were repetitive,
which means that it is probably a categorical attribute. You can find out what cate‐
gories exist and how many districts belong to each category by using the
value_counts() method:
>>> housing["ocean_proximity"].value_counts()
<1H OCEAN     9136
INLAND        6551
NEAR OCEAN    2658
NEAR BAY      2290
ISLAND           5
Name: ocean_proximity, dtype: int64
Let’s look at the other fields. The describe() method shows a summary of the
numerical attributes (Figure 2-7).
48 
| 
Chapter 2: End-to-End Machine Learning Project


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0078_img_01.png)

<!-- Pagina 79 -->
12 The standard deviation is generally denoted σ (the Greek letter sigma), and it is the square root of the var‐
iance, which is the average of the squared deviation from the mean. When a feature has a bell-shaped normal
distribution (also called a Gaussian distribution), which is very common, the “68-95-99.7” rule applies: about
68% of the values fall within 1σ of the mean, 95% within 2σ, and 99.7% within 3σ.
Figure 2-7. Summary of each numerical attribute
The count, mean, min, and max rows are self-explanatory. Note that the null values are
ignored (so, for example, the count of total_bedrooms is 20,433, not 20,640). The
std row shows the standard deviation, which measures how dispersed the values are.12
The 25%, 50%, and 75% rows show the corresponding percentiles: a percentile indi‐
cates the value below which a given percentage of observations in a group of observa‐
tions fall. For example, 25% of the districts have a housing_median_age lower than
18, while 50% are lower than 29 and 75% are lower than 37. These are often called the
25th percentile (or first quartile), the median, and the 75th percentile (or third
quartile).
Another quick way to get a feel of the type of data you are dealing with is to plot a
histogram for each numerical attribute. A histogram shows the number of instances
(on the vertical axis) that have a given value range (on the horizontal axis). You can
either plot this one attribute at a time, or you can call the hist() method on the
whole dataset (as shown in the following code example), and it will plot a histogram
for each numerical attribute (see Figure 2-8):
%matplotlib inline   # only in a Jupyter notebook
import matplotlib.pyplot as plt
housing.hist(bins=50, figsize=(20,15))
plt.show()
Get the Data 
| 
49


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0079_img_01.png)

<!-- Pagina 80 -->
The hist() method relies on Matplotlib, which in turn relies on a
user-specified graphical backend to draw on your screen. So before
you can plot anything, you need to specify which backend Matplot‐
lib should use. The simplest option is to use Jupyter’s magic com‐
mand %matplotlib inline. This tells Jupyter to set up Matplotlib
so it uses Jupyter’s own backend. Plots are then rendered within the
notebook itself. Note that calling show() is optional in a Jupyter
notebook, as Jupyter will automatically display plots when a cell is
executed.
Figure 2-8. A histogram for each numerical attribute
There are a few things you might notice in these histograms:
1. First, the median income attribute does not look like it is expressed in US dollars
(USD). After checking with the team that collected the data, you are told that the
data has been scaled and capped at 15 (actually, 15.0001) for higher median
incomes, and at 0.5 (actually, 0.4999) for lower median incomes. The numbers
represent roughly tens of thousands of dollars (e.g., 3 actually means about
$30,000). Working with preprocessed attributes is common in Machine Learning,
50 
| 
Chapter 2: End-to-End Machine Learning Project


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0080_img_01.png)

![Figura](images/page_0080_img_02.png)

<!-- Pagina 81 -->
and it is not necessarily a problem, but you should try to understand how the
data was computed.
2. The housing median age and the median house value were also capped. The lat‐
ter may be a serious problem since it is your target attribute (your labels). Your
Machine Learning algorithms may learn that prices never go beyond that limit.
You need to check with your client team (the team that will use your system’s out‐
put) to see if this is a problem or not. If they tell you that they need precise pre‐
dictions even beyond $500,000, then you have two options:
a. Collect proper labels for the districts whose labels were capped.
b. Remove those districts from the training set (and also from the test set, since
your system should not be evaluated poorly if it predicts values beyond
$500,000).
3. These attributes have very different scales. We will discuss this later in this chap‐
ter, when we explore feature scaling.
4. Finally, many histograms are tail-heavy: they extend much farther to the right of
the median than to the left. This may make it a bit harder for some Machine
Learning algorithms to detect patterns. We will try transforming these attributes
later on to have more bell-shaped distributions.
Hopefully you now have a better understanding of the kind of data you are dealing
with.
Wait! Before you look at the data any further, you need to create a
test set, put it aside, and never look at it.
Create a Test Set
It may sound strange to voluntarily set aside part of the data at this stage. After all,
you have only taken a quick glance at the data, and surely you should learn a whole
lot more about it before you decide what algorithms to use, right? This is true, but
your brain is an amazing pattern detection system, which means that it is highly
prone to overfitting: if you look at the test set, you may stumble upon some seemingly
interesting pattern in the test data that leads you to select a particular kind of
Machine Learning model. When you estimate the generalization error using the test
set, your estimate will be too optimistic, and you will launch a system that will not
perform as well as expected. This is called data snooping bias.
Creating a test set is theoretically simple: pick some instances randomly, typically
20% of the dataset (or less if your dataset is very large), and set them aside:
Get the Data 
| 
51


<!-- Imagenes detectadas en la pagina -->

![Figura](images/page_0081_img_01.png)

<!-- Pagina 82 -->

> [Error procesando con Ollama: [WinError 10061] No se puede establecer una conexión ya que el equipo de destino denegó expresamente dicha conexión]

13 In this book, when a code example contains a mix of code and outputs, as is the case here, it is formatted like
in the Python interpreter, for better readability: the code lines are prefixed with >>> (or ... for indented
blocks), and the outputs have no prefix.
14 You will often see people set the random seed to 42. This number has no special property, other than to be the
Answer to the Ultimate Question of Life, the Universe, and Everything.
import numpy as np
def split_train_test(data, test_ratio):
    shuffled_indices = np.random.permutation(len(data))
    test_set_size = int(len(data) * test_ratio)
    test_indices = shuffled_indices[:test_set_size]
    train_indices = shuffled_indices[test_set_size:]
    return data.iloc[train_indices], data.iloc[test_indices]
You can then use this function like this:13
>>> train_set, test_set = split_train_test(housing, 0.2)
>>> len(train_set)
16512
>>> len(test_set)
4128
Well, this works, but it is not perfect: if you run the program again, it will generate a
different test set! Over time, you (or your Machine Learning algorithms) will get to
see the whole dataset, which is what you want to avoid.
One solution is to save the test set on the first run and then load it in subsequent
runs. Another option is to set the random number generator’s seed (e.g., with np.ran
dom.seed(42))14 before calling np.random.permutation() so that it always generates
the same shuffled indices.
But both these solutions will break the next time you fetch an updated dataset. To
have a stable train/test split even after updating the dataset, a common solution is to
use each instance’s identifier to decide whether or not it should go in the test set
(assuming instances have a unique and immutable identifier). For example, you could
compute a hash of each instance’s identifier and put that instance in the test set if the
hash is lower than or equal to 20% of the maximum hash value. This ensures that the
test set will remain consistent across multiple runs, even if you refresh the dataset.
The new test set will contain 20% of the new instances, but it will not contain any
instance that was previously in the training set.
Here is a possible implementation:
from zlib import crc32
def test_set_check(identifier, test_ratio):
    return crc32(np.int64(identifier)) & 0xffffffff < test_ratio * 2**32
52 
| 
Chapter 2: End-to-End Machine Learning Project


<!-- Pagina 83 -->
15 The location information is actually quite coarse, and as a result many districts will have the exact same ID, so
they will end up in the same set (test or train). This introduces some unfortunate sampling bias.
def split_train_test_by_id(data, test_ratio, id_column):
    ids = data[id_column]
    in_test_set = ids.apply(lambda id_: test_set_check(id_, test_ratio))
    return data.loc[~in_test_set], data.loc[in_test_set]
Unfortunately, the housing dataset does not have an identifier column. The simplest
solution is to use the row index as the ID:
housing_with_id = housing.reset_index()   # adds an `index` column
train_set, test_set = split_train_test_by_id(housing_with_id, 0.2, "index")
If you use the row index as a unique identifier, you need to make sure that new data
gets appended to the end of the dataset and that no row ever gets deleted. If this is not
possible, then you can try to use the most stable features to build a unique identifier.
For example, a district’s latitude and longitude are guaranteed to be stable for a few
million years, so you could combine them into an ID like so:15
housing_with_id["id"] = housing["longitude"] * 1000 + housing["latitude"]
train_set, test_set = split_train_test_by_id(housing_with_id, 0.2, "id")
Scikit-Learn provides a few functions to split datasets into multiple subsets in various
ways. The simplest function is train_test_split(), which does pretty much the
same thing as the function split_train_test(), with a couple of additional features.
First, there is a random_state parameter that allows you to set the random generator
seed. Second, you can pass it multiple datasets with an identical number of rows, and
it will split them on the same indices (this is very useful, for example, if you have a
separate DataFrame for labels):
from sklearn.model_selection import train_test_split
train_set, test_set = train_test_split(housing, test_size=0.2, random_state=42)
So far we have considered purely random sampling methods. This is generally fine if
your dataset is large enough (especially relative to the number of attributes), but if it
is not, you run the risk of introducing a significant sampling bias. When a survey
company decides to call 1,000 people to ask them a few questions, they don’t just pick
1,000 people randomly in a phone book. They try to ensure that these 1,000 people
are representative of the whole population. For example, the US population is 51.3%
females and 48.7% males, so a well-conducted survey in the US would try to maintain
this ratio in the sample: 513 female and 487 male. This is called stratified sampling:
the population is divided into homogeneous subgroups called strata, and the right
number of instances are sampled from each stratum to guarantee that the test set is
representative of the overall population. If the people running the survey used purely
random sampling, there would be about a 12% chance of sampling a skewed test set
Get the Data 
| 
53