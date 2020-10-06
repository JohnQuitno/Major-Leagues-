Major Leagues
==============================

Predicting score of Royals Game

Project Organization
------------


    ├── data
    │   └── raw   
    │        │── mlb_elo_latest.csv                     
    │
    ├── notebooks          
    │   └── src.ipynb               


Data
----
We are using 538's data that they use in their baseball predictions. This is an interesting data set 
because it has kind of done a lot of the work already. They heave very descriptive fields that contain 
a lot of information. Some of the most interesting fields are the elo and pitcher rgs fields. The 
elo field uses an elo system to rank the teams. It goes through the games and either adds or subtracts
points from a teams elo score depending on win or loss and strength of opponent. The pitcher rgs score
also does some interesting things. It stands for "rolling games score" and looks how pitchers have done
in previous games and gives them a score accordingly.

Feature Engineering
-------------------
There wasn't a whole lot of feature engineering necessary with this data set for some of the reasons 
described above. If we were given raw data, like game statistics and pitcher statistics, we would have
been able to use those features to design somethings similar to 538's elo and pitcher rgs fields. These
contain the raw data and wrap them up into something thas is descriptive and powerful for use in the 
regression algorithms that we chose here.

Regression Algorithms
-------------------------

The first algorithm that I used was just a simple linear regression. This one was kind of interesting 
because of how correlated a lot of our input data was. We had things like team rating as well as elo. 
It was clear from the data that the elo and ratings for teams were highly correlated. This means that 
we probably don't want to use both of them in our regression. But, the fact that they are highly correlated
means that most of the information is contained in just one of the fields. I also used the pitcher's rgs.
This also has some correlation to the team elo, however, it is much lower and doesn't have such a negative
affect on the performance of the regression. I also used the gradient boosting algorithm. I don't quite 
understand the mechanics of this one as well. There are weak learners that are combined to create a strong 
learner. The algorithm runs successively until it converges. When it converges it combines these learners into
one. It did take longer to run, but there weren't too many data points so it wasn't prohibitively long.