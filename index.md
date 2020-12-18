# Welcome 

Together, we will try to understand how ratings given on Yelp influence everyday mobility. 
For our study, we will be using more than **+8M reviews** on **+200k businesses** made by **+196k** users. 

## A Light Introduction to the Dataset 
We are using a dataset published by Yelp, one of the most successfull Local Based Social Network as of today. On Yelp users share with the rest of the community their experience of any kind of businesses. You can find on Yelp multiple a wide variety of businesses, ranging from local mexican restaurants to the a funeral homes.  

{% if site.tags != "" %}
  {% include rating_distribution.html %}
{% endif %}

As we can see on the figure above, the mean rating of a business is 3.5. Also, as we can see, the 25k lowest reviews have a rating below 2 and the 25k best rated businesses have a grade of 5. Hence, we will consider a **bad rating, a rating less or equal to 2** and a **good rating, a rating equal to 5**. \
Next, we plot the number of checkins per category, depending on the rating of each business.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~PM_EPFL/3.embed"></iframe>







### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown

Syntax highlighted code block

# Header 1



## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](https://www.google.com/search?q=google+macaron&client=ubuntu&hs=y80&channel=fs&source=lnms&tbm=isch&sa=X&ved=2ahUKEwiahuzVzNXtAhUEHOwKHVqQAA0Q_AUoAXoECAcQAw&biw=1408&bih=642#imgrc=aLDlP6ipr6SLgM)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/zxyzz/ada_web/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
