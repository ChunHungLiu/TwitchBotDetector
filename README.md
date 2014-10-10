###How this works###
Essentially this is a bot that tries to detect streams with fake viewers via
the Twitch API and the power of statistics.

Primarily, it looks at certain metrics such as the ratio between chatters to reported viewers.
Alternative bot detection methods are listed below. Let me know if you see any other patterns in 
streams with fake chatters by [emailing me](mailto:popcorncolonel@gmail.com), or feel
free to contact me with questions/anything at that email address.

I'm not necessarily accusing the streamers of botting their own channels. I'm not affiliated with Twitch.

###Usage###
"python bdb.py"

Note: To run it locally (not send out tweets), set "tweetmode" to False in 
      global_consts.py.  
Modules needed:

* [Requests](http://docs.python-requests.org/en/latest/)

**If tweetmode**,  
* [Twython](http://twython.readthedocs.org/en/latest/)
* [Python-Twitter](http://code.google.com/p/python-twitter/)

###TODO###
* More sophisticated detection methods, including:
    -Sharp, significant increases in viewers without proportional increases in
     the number of chat users (take into account videos in the front page of
     Twitch.. maybe check the front page of Twitch to see which user is there?
     On average how many users are watching via the main twitch page?)
    -Take into account the average chat viewer ratio for each game per user: maybe a bad idea - skewed by bots
    -Long-term database storage of average viewer count
    -If the stream has more viewers than followers, there may be cause for concern.
    -More chatters than viewers, plus weird names/inactive chat => suspicion

* New heuristics for detecting chatbots: very low average follower count in
   chat (regarding how many people each user is following) is indicative of
   chatbots. Also if a lot of the bots have the exact same number (say, under 5).  
   Or, if most of the followers are following the exact same streams.  
   The main problems with these is that I need to individually access the
   Twitch servers for each chatter; this could take hours for certain streams
   with large viewer counts.

###TL;DR###
Go to http://www.twitter.com/BotDetectorBot!  
Program usage: "python bdb.py"

