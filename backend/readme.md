# Overview

You'll build some basic building blocks of an app that could help a group of people pick a movie to watch!

# Time
It's important to us that you spend at least one hour on this exercise, and NO MORE than three hours. Please [set a timer](https://www.google.com/search?q=timer+3+hours) for 3 hours and don't invest any additional time! This exercise is meant to be fodder for meaningful discussion with a real human, not a pass/fail or automate-able project submission.


# Features
Given our commitment to your time, please consider tackling these features in the order we've listed. That way, if you want to end a bit early, you'll have already addressed the pieces we think are the most interesting to discuss.

# Step 1: Model your data

Build tables/models to store your data. Use whatever database system you prefer (we used rails + sqlite), but please do use some sort of DBMS persistence (no raw files on disk or in memory, please!)

The app is interested in users and movies, and being able to save which users are interested in watching which movies. In addition you should be able to persist whether a user has watched a movie before. Please look ahead to the API sections for a better idea of how you will interact with this model.

# Step 2: Create a users API

Now that your data is modeled we're interested in how we might ask interesting questions about what is stored in your model.

Provide an API so that we can retrieve:
1. All the movies a specific user is interested in watching
2. All the movies a specific user has watched
3. All the movies a specific user is interested in watching or has watched

Provide enough data in the response that we could build a simple display, so at least a name. Use whatever format is most convenient for you (we returned JSON).

# Step 2: Create a movies API

Provide an API so that we retrieve:
1. All the movies
2. All the movies at least 1 user is interested in watching
3. All the movies ordered by the number of users interested in watching them

# Step 3: Create a suggestions API

Provide an API so that we can retrieve
1. Given two users, all the movies that both users are interested in watching

# Submission
* Add some instructions to help us get your code's programming language & dependencies installed
* Create a zip file of your repo (if you're using git, git archive --format=zip --output project.zip will do it for ya) and make it available to leith@meritamerica.org via your file-sharing service of choice (or just send it straight through email if it's not too big)

Thanks so much for your time and interest at working for Merit America! We'll be in touch soon.
