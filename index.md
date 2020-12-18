# Welcome 

Together, we will try to understand how ratings given on [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc) influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. 

## A Light Introduction to the Dataset 
We are using a dataset published by [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc), one of the most successfull Local Based Social Network as of today. On Yelp users share with the rest of the community their experience on any kind of businesses. You can find on Yelp a wide variety of businesses, ranging from local mexican restaurants to funeral homes.

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. The 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. <br>
Next, we plot the number of checkins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>

One can see that the most represented category is by far food buisnesses (i.e restaurants and groceries stores), followed by Entertainment (i.e museum, cinemas, art galery...). However, the distribition of the number of checkins per category varies depending on the rating of businesses.
When we look at the repartition of checkins for each categories, the distribution of checkins varies depending on the category. In the `Plot all Ratings`supblot, for food businesses, we can see that the checkin distribution is mostly centered around 4-stars ratings, while for automotive businesses, checkins are more spread-out across all ratings. 
This lead us to our first discovery (and hopefully not the last): TO DO    

Lets now dive into the real subject!

## Are we more likely to travel to good-rated businesses when traveling far from home?
Our first focal point will be the probability to travel to a good-rated business depending on the distance travelled from home. 
To 

##### How likely we are going to good rated business at a distance d from home?
{% if site.tags != "" %}
  {% include go_to_good_rated_business.html %}
{% endif %}

##### How likely we give good ratings to business at a distance d from home?
{% if site.tags != "" %}
  {% include give_good_ratings.html %}
{% endif %}


### Word of Mouth Impact on Mobility


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




