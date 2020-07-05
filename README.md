# Hacker News Post Analysis

Hacker News is a site started by the startup incubator Y Combinator, where user-submitted stories (known as "posts") are voted and commented upon, similar to Reddit. Hacker News is extremely popular in technology and startup circles, and posts that make it to the top of Hacker News' listings can get hundreds of thousands of visitors as a result.

[![img](https://news.ycombinator.com/yc500.gif)](https://news.ycombinator.com/newsguidelines.html)

In this project, a dataset containing the posts submitted on Hacker News till the date 26th September 2016 is categorized and analyzed. Initially, the posts are segregated based on the type of posts. For this project, the posts are segregated into the following three categories; 'Ask HN' Posts, 'Show HN' Posts, and other posts.

Users submit Ask HN posts to ask the Hacker News community a specific question. Below are a few examples:

Ask HN: How to improve my personal website?<br>
Ask HN: Am I the only one outraged by Twitter shutting down share counts?<br>
Ask HN: Aby recent changes to CSS that broke mobile?<br>

Similarly, users submit Show HN posts to show the Hacker News community a project, product, or just generally something interesting. Below are few of examples:

Show HN: Wio Link  ESP8266 Based Web of Things Hardware Development Platform'<br>
Show HN: Something pointless I made<br>
Show HN: Shanhu.io, a programming playground powered by e8vm<br>

In this project, the 'Ask HN' posts are analyzed based on the time and date of their creation using Python's 'DateTime' modules.

### Source of data
The data for this project is procured from Kaggle (Link: https://www.kaggle.com/hacker-news/hacker-news-posts)

### Exploring the dataset
The dataset has around data of more than 293K posts. Below are descriptions of the columns:
<li><b>id</b>: The unique identifier from Hacker News for the post
<li><b>title</b>: The title of the post
<li><b>url</b>: The URL that the posts link to if it the post has a URL
<li><b>num_points</b>: The number of points the post acquired, calculated as the total number of upvotes minus the total number of downvotes
<li><b>num_comments</b>: The number of comments that were made on the post
<li><b>author</b>: The username of the person who submitted the post
<li><b>created_at</b>: The date and time at which the post was submitted

### Segregating the data for analysis

In this section, the dataset is isolated into the three aforementioned categories. This is implemented using the in-built string 'startswith()' function. This function, along with the 'lower()' function (converts strings to lower case values) is used to identify posts with titles starting with 'ask hn' and 'show hn' and thus isolate the posts in the respective separate lists.

### Finding the average number of comments

The average number of comments per post for each type ('Ask HN', 'Show HN', and other posts) are calculated below.

### Finding the amount of 'Ask HN' posts & comments per hour
The number of comments for 'Ask HN' posts is naturally high since these posts, by their nature, drive users to answer the questions stated in them. In this project, further analysis is focussed on the 'Ask HN' posts.

The column 'created_at' indicates the time of the creation of each post. Inherently, the values in these columns are stored in the string datatype. Using the 'strptime' function of the 'datetime' module in python, these values are converted to 'DateTime' class. This enables the bifurcation of the values in the 'created_at' column with respect to the year, month, day as well as time (hour, minutes, etc.) of creation. 

Using the hour mark of the converted 'DateTime' class objects, the average number of posts created every hour as well as the average number of comments per hour are calculated in the section. 

### Results
FFrom the results, it can be observed that the highest number of posts, the highest number of comments, and the highest average number of comments per hour per post are between 3 pm (1500 hours) to 4 pm (1600 hours). On the other hand, the least number of comments are the lowest average number of comments per hour per post are witnessed on the Hacker News platform during the timeframe of 9 am (0900 hours) to 10 am (1000 hours). The cause for the latter may be attributed to the starting time of workday for most users since this platform is predominantly used by a workforce in the technology domain.

The results also indicate a trend where a higher activity is noticed on the Hacker News platform commencing from the second half of a workday (1 pm or 1300 hours) onwards. 

### Pickle result to another file
In case if further analysis is to be performed at a later point of time, the variable 'comments_table_sorted' is pickled and stored (dumped) in the file 'hacker_news_pickle'.
