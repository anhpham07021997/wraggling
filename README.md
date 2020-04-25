# Wraggling

### This project is part of Udacity Data Nanodegree program
### Introduction 
#### The Data
##### 1)Enhanced Twitter Archive
The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo). **The ratings probably aren't all correct. Same goes for the dog names and probably dog stages (see below for more information on these) too**. You'll need to assess and clean these columns if you want to use them for analysis and visualization.
##### 2)Additional Data via the Twitter API
Back to the basic-ness of Twitter archives: `retweet count` and `favorite count` are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. 
##### 3)Image Predictions File
neural network that can classify breeds of dogs. The results: a table full of image **predictions (the top three only)** alongside each **`tweet ID`, `image URL`, and the `image number` that corresponded to the most confident prediction** (numbered 1 to 4 since tweets can have up to four images).
-tweet_id is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921

-p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever

-p1_conf is how confident the algorithm is in its #1 prediction → 95%

-p1_dog is whether or not the #1 prediction is a breed of dog → TRUE

-p2 is the algorithm's second most likely prediction → Labrador retriever

-p2_conf is how confident the algorithm is in its #2 prediction → 1%

-p2_dog is whether or not the #2 prediction is a breed of dog → TRUE
etc.
#### Tasks
> Data wrangling, which consists of:
- Gathering data (downloadable file in the Resources tab in the left most panel of your classroom and linked in step 1 below).
- Assessing data:  ***assess and clean at least 8 quality issues and at least 2 tidiness issues in this dataset.***
- Cleaning data in `wrangle_act.ipynb`
> Storing, analyzing, and visualizing your wrangled data in `twitter_archive_master.csv`
- **three (3) insights and one (1) visualization**
> Reporting on 1) your data wrangling efforts and 2) your data analyses and visualizations
- 300-600 word writtern report `wrangle_report.pdf/html` => decribe wrangling effort-internal
- at least 250 word `act_report.pdf/html` communicate insight display visualiztion-external (blog and magazine)

### Key Points
- **original ratings (no retweets) that have images.** 
- Cleaning :**merging** according to the **rules of tidy data.**
- The fact that the rating numerators are greater than the denominators does not need to be cleaned.
- **You do not need to gather the tweets beyond August 1st, 2017**

## Clean


## Tidiness

### Archive data 


- 1)`rating_numerator`,`rating_denominator` are redundant => combine to 1 columns named `rating`=>need to merge 3 tables
- 2)`doggo` `floofer`, `pupper`,`puppo` are redundant=> melt data combine to 1 columns




## Quality

### Archive data 
-  1)missing record on `in reply to user id/user_status`,`retweeted_status_id/user_id`,`retweeted_status_timestamp` are NA=> drop 
- 2) remove +000 in `imestamp` data 

- 3) `timestampt` is not datatime=> change to time data 

- 4)`name` has strange name like 'a' 'an' 'the' 'by'  quite,actually, just,one,his,my,very, not=>replace with NONE

- 5)OliviÃ©r, old, RalphÃ©, AmÃ©lie,GÃ²rdÃ³n,,FrÃ¶nq,getting, DevÃ³n=> change to proper names
- 6)`expand_url` NA - mean no tweet you retweet => drop to combine: 3 tables 
- 7)replace the source content by ‘Twitter for iphone’, ‘Vine - Make a Scene’, ‘Twitter Web Client’, and ‘TweetDeck’.


###  predict data
 
- 8)Capitalize first Letter of name for consitance, replace '_' with space , add space in name of bread in p1 p2 p3 



### Library
This project is my practice for data wraggling including:
- Gathering data
  - tsv
  - json
  - web scraping :twitter
  - txt


### Related files
- wrangle_act.ipynb: code for gathering, assessing, cleaning, analyzing, and visualizing data
- wrangle_report.pdf or wrangle_report.html: documentation for data wrangling steps: gather, assess, and clean
- act_report.pdf or act_report.html: documentation of analysis and insights into final data
- twitter_archive_enhanced.csv: file as given
- image_predictions.tsv: file downloaded programmatically
- tweet_json.txt: file constructed via API
- twitter_archive_master.csv: combined and cleaned data
### License 
MIT
