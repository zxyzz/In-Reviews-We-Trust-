# Welcome 

Together, we will try to understand how ratings given on [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc) influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. 

## A Light Introduction to the Dataset 
We are using a dataset published by [Yelp](https://www.yelp.com/dataset/documentation/main?fbclid=IwAR1RgySn5BU9FaD_5TkJ0Rxqs-hIoEQqEC5CSm9kzXka7boJj8YVTRyDvYc), one of the most successfull Local Based Social Network as of today. On Yelp users share with the rest of the community their experience of any kind of businesses. You can find on Yelp multiple a wide variety of businesses, ranging from local mexican restaurants to the a funeral homes.

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. Also, as we can see, the 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. \
Next, we plot the number of checkins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>



## Our Researches

<! words of mouth>
### Word of Mouth Impact on Friends’ Recommendations




### Word of Mouth Impact on Weekdays
{% if site.tags != "" %}
  {% include weekday.html %}
{% endif %}


### Word of Mouth Impact on Categories of Businesses
{% if site.tags != "" %}
  {% include category.html %}
{% endif %}

### "Treated" and "Non-Treated"




