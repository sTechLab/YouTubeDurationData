# Two Datasets of A Data-driven Study of View Duration on YouTube
We share a set of random YouTube videos crawled from the Web and a set of videos watched by participants tracked by a Chrome extension that were used to examine whether and how indicators of collective preferences and reactions are associated with view duration of videos.

If you use either the *Random Videos* dataset or *Individual Logs* dataset in your research, please cite the paper. For example: 

##### Park, M., Naaman, M., & Berger, J. (2016). A Data-driven Study of View Duration on YouTube. Tenth International Conference on Web and Social Media (ICWSM 2016). Cologne, Germany, May 2016.

For questions, please contact:

**Minsu Park**

Social Technologies Lab (https://s.tech.cornell.edu/)

Jacobs Institute, Cornell Tech

minsu [at] jacobs [dot] cornell [dot] edu 


## Description:
This dataset contains the video properties and sentiment of comments for each of the videos collected through the YouTube API. We also include the average watch duration for each video (for both randomly selected videos and videos watched by our participants) and dwell time of individual users. Details of the data collection and process procedures are provided in the paper.

### Data Collection Procedures:
**Format – variable (name of the variable in the data table)**

####Random Videos:
This dataset is a sample of 1,125 random videos from YouTube. We first obtained 100,000 randomly sampled YouTube videos through [Random YouTube]( http://randomyoutube.net), a site that collects IDs of the 10 most recently uploaded videos every fifteen minutes. We then retrieved the video properties for each of the videos through the YouTube API. To find the average watch duration for each video, we scraped the YouTube video page to get the aggregate watch duration available on the video page statistics tab. This step resulted in 44,766 videos. Other videos were either private videos, were deleted, or did not provide aggregate statistics. Finally, to ensure proper measurement of sentiment, we required videos in our sample to have at least five English comments, resulting in a final set of 1,125 videos.

For the *Random Videos* dataset, our view duration dependent variable was computed using the video's average view duration: the aggregate view duration of the video (as reported by YouTube) divided by the view count, both reported over the video's lifetime.
Here are variables of *Random Videos* (1,125 videos):

(1) View duration and video properties:
video id (video_id), view count (viewCount), favorite count (favoriteCount), like count (likeCount), dislike count (dislikeCount), share count (numShare), number of subscriber (numSubscriber), video duration (duration), posting date (publishedAt), elapsed time between posting and data collection dates (elapsed_time), video category (category_term), aggregated watch duration (watchTime), average view duration (averageViewDuration), number of comments (numParent), number of replies on any comments (numChild), number of English comments (num_EnglishComments), proportion of view duration (engagement), comments per view (comment_percentage), discussion density (discussion_density), likes per view (like_percentage), dislikes per view (dislike_percentage), like-dislike ratio, shares per view (share_percentage)

(2) Linguistic characteristics of comments including sentiment computed by LIWC:
funct, pronoun, ppron, i, we, you, shehe, they, ipron, article, verb, auxverb, past, present, future, adverb, preps, conj, negate, quant, number, swear, social, family, friend, humans, affect, posemo, negemo, anx, anger, sad, cogmech, insight, cause, discrep, tentat, certain, inhib, incl, excl, percept, see, hear, feel, bio, body, health, sexual, ingest, relativ, motion, space, time, work, achieve, leisure, home, money, relig, death, assent, nonfl, filler, WC, WPS, Sixltr, Dic, Numerals, Period, Comma, Colon, SemiC, QMark, Exclam, Dash, Quote, Apostro, Parenth, OtherP, AllPct

For more information about LIWC, see [http://liwc.wpengine.com](http://liwc.wpengine.com)

(3) Sentiment of comments computed by VADER:
neg, neu, pos, compound

For more information about VADER, see [https://github.com/cjhutto/vaderSentiment](https://github.com/cjhutto/vaderSentiment)

####Individual Logs:
The *Individual Logs* dataset is a set of 1,814 videos watched over several weeks by a sample of 158 participants recruited from [Task Rabbit](http://taskrabbit.com). To obtain this individual-level data, we developed and deployed a Chrome extension that collected how long each user spent each YouTube video page they visited, as well as other YouTube video information available at the time of the viewing. The extension recorded a view timestamp, video properties, and dwell time in each viewing session. The extension was installed and used by 189 participants who had a previous experience with YouTube, over a span of at least two weeks (our sample included 77 male and 112 female participants; there were no significant gender differences in usage of the extension). Using this extension, we collected a total of 17,599 video view sessions. We filtered videos which had missing information, were private, deleted, or did not have at least five English comments. We only kept videos where the participant's dwell time was not greater than the video duration to avoid unusually long dwell time due to potential errors (e.g., unexpected disconnections). The final dataset, as mentioned above, included 1,814 video view sessions. Note that we examined different cutoffs on dwell time from 1.5 times to 3 times longer than the video duration with truncation at 1 and found no impact on our key findings.

For the *Individual Logs* dataset, our view duration dependent variable was computed differently. In this case, we have used an individual, but approximate, view duration measurement. In particular, we used the user's dwell time for each video on the video's page, as was measured by the extension, as an approximation for the actual view time for the video by that user. 

Here are variables of *Individual Logs* (1,814 videos from 158 participants):

*Individual Logs* dataset contains same variables as *Random Videos* dataset. Additionally, this dataset includes individual user’s id (user_id), their gender (user_gender), ZIP code (user_zip), dwell time (dwell_time), and the fact whether they have clicked like (like) or dislike (dislike). 

As mentioned earlier, there are slight differences: elapsed time is the time difference between posting and watching dates. So, a timestamp of watching (watchedAt) is also included. Also, proportion of view duration (engagement) is computed based on dwell time, NOT average view duration.
		

