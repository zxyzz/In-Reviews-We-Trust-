# Welcome 

Together, we will try to understand how ratings given on [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc) influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. <br>
<br>
![Image](/img.jpg)

## Previous Work
This is a creative extension on the [paper](http://ial.eecs.ucf.edu/Reading/Papers/Friendship%20and%20Mobility%20User%20Movement%20In%20Location-Based%20Social%20Networks.pdf) ***Friendship and Mobility: User Movement in Location-Based Social Networks*** by **Eunjoon Cho**, **Seth A. Myers** and **Jure Leskovec**, which attempts to model human mobility using periodic and friendship induced movement. The dataset used in this paper is pretty similar to ours, based mainly on check-ins made on two localilty based social networks (Brightkite and Gowalla) as well as some cell phone communication data. One of the main points of this paper was studying the influence of friendship on mobility. Interestingly, the paper came to the conclusion that friendships do have a pretty notable impact on mobility, especially long distance travelling. Here are some very interesting insights shown in the paper:
* The probability of visiting a friend’s home reaches a plateau after the first 100km (around 0,3)
* If people moved randomly, then the farther away their are from their home, then the least likely they are to be in the vicinity of a friend
* The two above insights lead to the following conclusion: as the distance from home grows, so does the influence of friends. Indeed long distance travel is often linked to existing friendships

> In our work, we will be adding another component to this analysis, by using a dataset containing ratings: do business ratings affect our mobility? How does  a rating from a friend affect our mobility? All of this could be some very valuable information for business owners when it comes to their online presence on apps like Yelp!

---

## A Light Introduction to the Dataset 
We are using a dataset published by [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc), one of the most successful locality based social networks as of today. On Yelp users share with the rest of the community their experience with any kind of business. You can find on Yelp a wide variety of businesses, ranging from local mexican restaurants to funeral homes.

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. The 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. <br>
Next, we plot the number of check-ins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>

One can see that the most represented category is by far food businesses (i.e restaurants and groceries stores), followed by entertainment businesses (i.e museum, cinemas, art gallery etc). However, when we look at the distribution of check-ins for each category, the distribution of check-ins varies depending on the category. On the `Plot all Ratings` subplot, for food businesses, we can see that the check-in distribution is mostly centered around 4-stars ratings, while for automotive businesses, check-ins are more spread-out across all ratings. This yields a different category distribution depending on the business ratings. To see this difference, we encourage you to go through some subplots of the figure above.  

Now that we have a rough idea of the data let's dive into the real subject!

---

## Are we more likely to Travel to Good-Rated Businesses when Traveling far from Home?
Our first focal point will be to study the probability to travel to a well-rated business depending on the distance travelled from home (P\[business_grade = 5 | distance\]). 
This will help us understand how far people are willing to travel for a well-rated business. 

{% if site.tags != "" %}
  {% include go_to_good_rated_business.html %}
{% endif %}

The plot above shows that up-to the 100 km mark we are increasingly likely to visit a well-rated business, however, past the 100 km mark, this probability decreases sharply (with respect to the overall difference of the graph). 


> This leads us to our first discovery (and hopefully not the last): for well known places (in a 100 km range around our home) we are willing to travel further to go to a well-rated business. However, past that 100 km mark, people seem to enter in less known areas, and the importance of the business grade is less significant. 

---

## Word of Mouth Impact on Mobility
The past conclusion shows that mean ratings published on  public businesses Yelp pages are a real incentive to move to further places up-to the 100 km mark. So one could think: that’s it, I don’t need to brush up my public online image for users that are living far away. 
However, this conclusion would be quite wrong. Yelp reviews are not only passed down by public business pages, but are also shared among friends. And we will soon see that a good review made by a friend on a business is a strong incentive to visit that particular business.  
So we will now study **how a friend recommendation influences our movements**. 

#### Evolution of Friends' Review Influence on Mobility
First, we will plot the probability that when we travel far from home to a business, a friend left a positive or negative review on that business.  
This will help us understand how friend’s recommendations influence our far from home travels.

{% if site.tags != "" %}
  {% include friends_recomm_influence.html %}
{% endif %}

First, we can see that there is a consistent gap between the probability to travel to a well-rated business by a friend and one poorly rated. So far, good, we are rational, and avoid visiting poorly-rated businesses. 
We don’t observe the same kick-down past 100 km, showing that reviews made by friends, even for businesses that are located far from our home, are a strong driving force behind our movement. 

> It appears that well-reviewed businesses by friends increase quite significantly our chances to visit these businesses (with respect to other businesses). This effect is also known as the “word of mouth” effect, and we confirm that this effect is not a legend! From a business perspective, taking care of one customer increases the chance that one of his friends will come visit your business!

#### Evolution of Friends' Reviews Influence on Mobility According to Weekdays
We will now try to leverage the probability of visiting a friend’s recommended business with week-days. The idea is that depending on the day of the week, the influence of friends reviews might be more or less important, for example during the week-ends, we would expect to see a rise in friends' reviews’ influence.

{% if site.tags != "" %}
  {% include evolution_weekday.html %}
{% endif %}

As we can see on the different subplots, week-days do not influence the weight of a friend’s review on our mobility: no matter the day, a user will be quite likely to visit a business that has been well reviewed by a friend before, way more than a business that got bad reviews from friends. 

> The word of mouth effect is not time dependent, no matter the day, it's always a strong driving force behind a user's mobility. 

#### Evolution of Friends' Reviews Influence on Mobility According to Categories of Businesses
Right. So leveraging the probability of visiting a friend's well-reviewed business with week-days is somewhat inconclusive. However, we will now try to single out categories of businesses that should be especially aware of the word-of-mouth effect.    
To do so, we will plot for each category the probability that when traveling to a certain distance we will visit a friend’s well/poorly-reviewed business. 
 
{% if site.tags != "" %}
  {% include evolution_category.html %}
{% endif %}

We strongly encourage you to scroll through the different subplots of the above figure, results are quite surprising and interesting!    
For Real Estate and Manufacturing categories, both the probabilities of doing a check-in after a good friend review and bad friend review get really close to each other as distance gets higher. This means that as distance gets higher the opinion of a friend on a business isn't really important for these categories.  
In sharp contrast with the Real Estate category stand categories such as Food or Entertainment. These are the two categories with the biggest gap between the two curves. Meaning that the friend's opinion has the most influence here, regardless of the distance, which is what we would have expected for those two categories. Indeed, food and entertainment particularly, if well reviewed by friends, are more likely to make people move further: if an excellent restaurant or a great escape game a friend recommended is far away, the user still might go (when they wouldn't really if the friend gave a bad review).

> Depending on the business category, friend’s reviews have more or less importance. So the word-of-mouth effect only applies to some categories, with a variable degree of importance.  

---

## Influence of Weekdays on Mobility
We have seen that depending on weekdays, the influence of friends reviews doesn't really change. This leads us to ask: does mobility change on weekdays, independently on reviews? 

{% if site.tags != "" %}
  {% include weekday_influence.html %}
{% endif %}

As you can see, the weekday has some form of influence, especially on long distance travels! On the weekends, the probability of travelling to a certain distance goes up pretty consistently as the distance grows, before dropping at the 100 km mark. But for most other weekdays, it’s the other way round: the probability of travelling to a certain distance goes down with the distance before going back up at the 100km mark. This, indeed, is something expected, as during the week-end, people will more likely travel further from home (e.g week-end trips, beach days), but not too far (100 km mark). However on weekdays, we are more likely to stay close to home (e.g school, work), or really far, more than 100km (e.g business trips, vacations).


---

## Do Well Rated Businesses Manage to Attract more People?
Finally, to wrap up our study, we will place ourselves from the point of view of businesses, and see if businesses that are well-graded attract more people, than businesses poorly-rated. 
We will monitor the probability that a business attracts a certain amount of people, leveraged on the fact if it is a well-rated business (treated), or a poorly-rated business (control). 

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/8.embed"></iframe>

As we can see on the plot above, the treated businesses (with good reviews) have a higher chance of attracting more people than the ones that were not treated (with good reviews). 

> It appears that treated businesses (with a high mean rating) attract more people than poorly rated businesses. 

However, if we scroll back to the category distribution depending on ratings, we will see that the distribution of businesses per category is quite different depending if you are a well-rated business or a poorly rated business. 

> This means we are not comparing the same type of businesses in the treared and controlled group. 

So now, let’s try to plot the same distributions but for each category. 

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/5.embed"></iframe>

We can see that ratings have a lot of influence on businesses that provide food services or entertainment services, whereas businesses such as Real Estate agencies are less influenced by ratings.   
  
> We can thus refine our previous conclusion: having a good review helps certain categories of businesses but some are immune to good/bad reviews.  

--- 

## Final Words

