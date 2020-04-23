=Introduce=
    Hi. My name is Long
    My background is Computer Science. I graduated from Hanoi University of Science and Technology in 2018
    and have 2 years experience as a Software Engineer.
    Currenly I am software engineer at Tiki Corporation and I am doing a project about the recommendation system

    The main goal of this project is suggest relevant products, or category or keywords for the users. Maybe 
    user will have interest about it and want to buy it

=My job=
    * We have 2 main difference parts.
        - The training job. In which we calculate user data interaction like click, view, purchase 
            and use some ML algorithm to train and get the feature_vectors of user and also products. Then 
            save it to db
        - We use a model called hybrid model. That is the combination from content based model and collaborative filtering model
        - It means you will use both products features + interaction info

    * The web service where we get data from db for each user and return it


    * My main responsibility is the web service and a part of the training job.
    First 2 parts is share same python source. I seperate the web service and use java
    Training job of the project. But there are still
    many things to improve. 
        - Customize the sql so we can gather more user data to train.
        - From _ga we saw that 75% of users just interact with 1 category in 1 session. So that's important 
            to predict realtime result for users
        - So need to get data_user interaction realtime...
