# Welcome 

Together, we will try to understand how ratings given on [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc) influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. 
---
## A Light Introduction to the Dataset 
We are using a dataset published by [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc), one of the most successfull Local Based Social Network as of today. On Yelp users share with the rest of the community their experience on any kind of businesses. You can find on Yelp a wide variety of businesses, ranging from local mexican restaurants to funeral homes.

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. The 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. <br>
Next, we plot the number of checkins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>

One can see that the most represented category is by far food buisnesses (i.e restaurants and groceries stores), followed by Entertainment (i.e museum, cinemas, art galery...). However,when we look at the repartition of checkins for each categories, the distribution of checkins varies depending on the category. In the `Plot all Ratings`supblot, for food businesses, we can see that the checkin distribution is mostly centered around 4-stars ratings, while for automotive businesses, checkins are more spread-out across all ratings. This yields to different category distribution depending on the business ratings. To see this difference, we encourage you to go through some subplots of the figure above.  

Now that we have a rough idea of the data lets dive into the real subject!

---
## Are we more likely to travel to good-rated businesses when traveling far from home?
Our first focal point will be to study the probability to travel to a well-rated business depending on the distance travelled from home ($P(business_grade = 5 | distance)$). 
This is will help us understand how far people are willing to travel for a well-rated business. 


{% if site.tags != "" %}
  {% include go_to_good_rated_business.html %}
{% endif %}

The plot above shows that up-to the 100km mark we are *increasingly likely to visit a well-rated palce*, however, past the 100km mark, this probability decreases sharply (with respect to the overall difference of the graph). 


> This lead us to our first discovery (and hopefully not the last): for well known places (in a 100 km around their home) we are willing to travel further to go to a > well rated business. However, past that 100 km mark, people seem to enter in less known area, and the importance of the business grade is less significant. 


### Word of Mouth Impact on Mobility
The past conclusion shows that mean ratings on Yelp are a real incentive to move to further places up-to the 100 km mark. 

##### Evolution of friends' reviews influence on mobility
{% if site.tags != "" %}
  {% include friends_recomm_influence.html %}
{% endif %}


##### Evolution of friends' reviews influence on mobility according to weekdays
{% if site.tags != "" %}
  {% include evolution_weekday.html %}
{% endif %}

##### Evolution of friends' reviews influence on mobility according to categories of business
{% if site.tags != "" %}
  {% include evolution_category.html %}
{% endif %}

### Influence of Weekdays on Mobility
{% if site.tags != "" %}
  {% include weekday_influence.html %}
{% endif %}


### "Treated" and "Non-Treated"

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/5.embed"></iframe>

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/8.embed"></iframe>

