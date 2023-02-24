# We Dogs Data
## by Praprara Owodeha-Ashaka


## Dataset

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ tweets from @dog_rates. The tweet text contains ratings of dogs usually over 10. The dataset here has the tweet text and timestamp with dog names, rating numerator and denominator, dog type extracted from the text. Some of the dog names and dog types were incorrectly extracted. This project's aim was to identify and clean.

I was required to extract the retweet count and favorite count information of each tweet using twitter's API, save this as tweet_json.txt and add it to the original data as new columns.

The third data source was a TSV file containing each tweet and the top three predicted content of the image. The predictions were made by a neural network

My task was to Identify and fix 8 quality issues and 2 tidyness issues.


## Summary of Findings

### Quality issues

1. in the archive data, many dog names that are written as  one of these are actually supposed to be 'None', because the dog names weren't specified: 

       ['a', 'actually', 'all', 'an', 'by', 'his', 'life', 'light', 'mad', 'my', 'not', 'old', 'one', 'quite', 'space', 'the', 'this', 'unacceptable', 'very']

2. The 'timestamp' and 'retweeted_status_timestamp' columns have a wrong datatype (object instead of datetime). The tweet_id column should also be a string object

 3 - 4 . Wrong rating numerator
 

3. in the archive data, the tweet with ID 832215909146226, numerator is 75 instead of 9.75

4. in the archive data, the tweet with ID 667550882905632, numerator is 5 instead of -5

 5 - 7. Wrong Numerator AND Denominator
 

5. in the archive data, the tweet with ID 722974582966214, numerator is 4 and denominator is 20, instead of 13/10

6. in the archive data, the tweet with ID 775096608509886, numerator is 9 and denominator is 11, instead of 14/10

7. in the archive data, the tweet with ID 666287406224695, numerator is 1 and denominator is 2, instead of 9/10

 8 - 9. Only part of dog names gotten
 

8. in the archive data, the tweet with ID 775096608509886, the dog's actual name is O'Malley, but it's written as just 'O'

9. in the archive data, the tweet with ID 770414278348247, the dog's actual name is Al Cabone, but it's written as just 'Al'

 10 - 14. Dog name totally wrong
 

10. in the archive data, the tweet with ID 765395769549590, the dog's actual name is Zoey, but it's written as 'my'

11.  in the archive data, the tweet with ID 748977405889503, there's no dog, so the name should be 'None', not "not"

12. in the archive data, the tweet with ID 748692773788876, the dog's actual name is Quizno, but it's written as just 'his'

13. in the archive data, the tweet with ID 671743150407421, the dog's actual name is Jacob, but it's written as just 'a'

14. in the archive data, the tweet with ID 667177989038297, the dog's actual name is Daryl, but it's written as just 'a'

 15-17. Dog name wrongly said to be 'None'

15. in the archive data, the tweet with ID 775096608509886, the dog's actual name is Bretagne, but it's written as 'None'

16. in the archive data, the tweet with ID 856526610513747, the dog's actual name is CHARLIE, but it's written as 'None'

17. in the archive data, the tweet with ID 675870721063669, the dog's actual name is Yoshi, but it's written as 'None'


18. For all the tweets that contain the text 'named', the names were identified wrongly. The actual names are the words that come just after 'named' in the tweets. The exception is the one that contains "Named", starting with capital letters. The name of that one is Wilson

19. There are 181 rows that are about data which are retweets

# Tidyness Issues
### Issue #1: The data in tweet_json.txt should be part of the archive table

### Issue #2: Each dog type makes a column