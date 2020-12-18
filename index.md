# Welcome 

Together, we will try to understand how ratings given on [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc) influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. 
---
## Previous Work
This is a creative extension on the [paper](http://ial.eecs.ucf.edu/Reading/Papers/Friendship%20and%20Mobility%20User%20Movement%20In%20Location-Based%20Social%20Networks.pdf) **Friendship and Mobility: User Movement in Location-Based Social Networks** by **Eunjoon Cho**, **Seth A. Myers
** and **Jure Leskovec**, which attempts to model human mobility using periodic and friendship induced movement. The dataset used on this paper is pretty similar to ours, based mainly on check-ins made on two local based social networks (Brightkite and Gowalla) as well as some cell phone communication data. One of the main points of this paper was studying the influence of friendship on mobility. Interestingly, the paper came to the conclusion that friendships do have a pretty notable impact on mobility, especially long distance travelling. Here are some very interesting insights shown in the paper :
* The probability of visiting a friend’s home reaches a plateau after the first 100km (around 0,3)
* If people moved randomly, then the farther away their are from their home, then the least likely they are to be in the vicinity of a friend
* The two above insights lead to the following conclusion: as the distance from home grows, so does the influence of friends. Indeed long distance travel is often linked to existing friendships.

>In our work, we will be adding another component to this analysis, by using a dataset containing ratings : do business ratings affect our mobility ? How does  a >rating from a friend affect our mobility? All of this could be some very valuable information for business owners when it comes to their online presence on apps >like Yelp!
---

## A Light Introduction to the Dataset 
We are using a dataset published by [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc), one of the most successful Local Based Social Network as of today. On Yelp users share with the rest of the community their experience on any kind of business. You can find on Yelp a wide variety of businesses, ranging from local mexican restaurants to funeral homes.

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. The 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. <br>
Next, we plot the number of checkins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>

One can see that the most represented category is by far food businesses (i.e restaurants and groceries stores), followed by Entertainment (i.e museum, cinemas, art gallery...). However,when we look at the distribution of check-ins for each category, the distribution of checkins varies depending on the category. In the `Plot all Ratings`subplot, for food businesses, we can see that the check-in distribution is mostly centered around 4-stars ratings, while for automotive businesses, check-ins are more spread-out across all ratings. This yields a different category distribution depending on the business ratings. To see this difference, we encourage you to go through some subplots of the figure above.  

Now that we have a rough idea of the data let's dive into the real subject!

---
## Are we more likely to travel to good-rated businesses when traveling far from home?
Our first focal point will be to study the probability to travel to a well-rated business depending on the distance travelled from home ($P(business_grade = 5 | distance)$). 
This will help us understand how far people are willing to travel for a well-rated business. 

{% if site.tags != "" %}
  {% include go_to_good_rated_business.html %}
{% endif %}

The plot above shows that up-to the 100km mark we are increasingly likely to visit a well-rated business, however, past the 100km mark, this probability decreases sharply (with respect to the overall difference of the graph). 


> This leads us to our first discovery (and hopefully not the last): for well known places (in a 100 km around their home) we are willing to travel further to go to a > well rated business. However, past that 100 km mark, people seem to enter in less known area, and the importance of the business grade is less significant. 


## Word of Mouth Impact on Mobility
The past conclusion shows that mean ratings published on businesses Yelp pages are a real incentive to move to further places up-to the 100 km mark. So one could think: that’s it, I don’t need to brush up my public online image for user’s that are living far away. 
However, this conclusion would be quite wrong. Yelp reviews are not only passed down by public business pages, but are also shared among friends. And we will soon see that a good review made by a friend on a business is a strong incentive to visit that particular business.  
So we will now study **how a friend recommendation influences our movements**. 

#### Evolution of friends' reviews influence on mobility

{% if site.tags != "" %}
  {% include friends_recomm_influence.html %}
{% endif %}


### Influence of Weekdays on Mobility
{% if site.tags != "" %}
  {% include weekday_influence.html %}
{% endif %}


#### Evolution of friends' reviews influence on mobility according to weekdays

{% if site.tags != "" %}
  {% include evolution_weekday.html %}
{% endif %}


#### Evolution of friends' reviews influence on mobility according to categories of business
{% if site.tags != "" %}
  {% include evolution_category.html %}
{% endif %}



### "Treated" and "Non-Treated"

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/8.embed"></iframe>


<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/5.embed"></iframe>
