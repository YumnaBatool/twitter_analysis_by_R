# twitter_analysis_by_R
Getting tweets of a User to analyze 

STEPS:

GETTING TWITTER API
1- Sign in Twitter
2- Go to https://apps.twitter.com/ 
3- Fill the form, fill "Website" by you any blog etc, leave "Callback URL" empty and create app
4- Note the API Key also API Key Secret by clicking "manage keys..."

R TWITTER AUTHENTICATION CODE:
1- Install packages ROAuth, RCurl, bitops, rjson, twitteR,
2- Load "twitteR" library
  # twitter_analysis_by_R
Getting tweets of a User to analyze 

STEPS:

GETTING TWITTER API
1- Sign in Twitter
2- Go to https://apps.twitter.com/ 
3- Fill the form, fill "Website" by you any blog etc, leave "Callback URL" empty and create app
4- Note the API Key also API Key Secret by clicking "manage keys..."

R CODE:
1- Install packages ROAuth, RCurl, bitops, rjson, twitteR,
2- Load "twitteR" library
  >library(twitteR)
3- Download the curl certificate needed for twitter authentication
  >download.file(url="http://curl.haxx.se/ca/cacert.pem", destfile="cacert.pem")
4- Set the twitter certificate
  >requestURL <- "https://api.twitter.com/oauth/request_token"
  >accessURL <- "https://api.twitter.com/oauth/access_token"
  >authURL <- "https://api.twitter.com/oauth/authorize"
5- Define you API key and secret 
  >ApiKey <- "YOUR API KEY"
  >KeySecret <- "YOUR API KEY SECRET"
6- Set the authentication function as
  > twitCred <- OAuthFactory$new(consumerKey=ApiKey, consumerSecret=KeySecret, requestURL=requestURL, accessURL=accessURL, authURL=authURL)
7- Accessing twitter
  >twitCred$handshake(cainfo="cacert.pem")
  #you will be directed to authorize page in browser click "authorize" note the pin
8- Enter the pin in R after "....here:" You will see it in R
9- Verify authentication 
  >registerTwitterOAuth(twitCred)
  [1] TRUE
10- Save this authentication as file for future use, it help you to skip this process in future
  >save(list="twitCred", file="twitter_authentication")
11- Every time you start twitter analysis just load the authentication file
  >library (twitteR)
  >load("twitter_authentication")
  >registerTwitterOAuth(twitCred)
12- Getting tweets of a user
  >Ronaldo <- searchTwitter('@Cristiano', cainfo="cacert.pem")
13- You can see tweets by Ronaldo by
  >head(Ronaldo)
  
[[1]]
[1] "GigaTools: DJ Soulninja is playing @ #Zero Gravity #Dubai #United Arab Emirates, Thu 22 Jan 2015 @ 21:00  #gigs"

[[2]]
[1] "sot_erika_13: RT @Spirit_ofTexas: Purple Royalty is on their way to The MAJORS! @MAJORScheer í ½í²œ #MediumCoed #United"

[[3]]
[1] "pdicey: https://t.co/E7fQFUFipD #everything #recycle #famousrecords #music #hiphop #united"

[[4]]
[1] "wendy_kizer: RT @Spirit_ofTexas: Purple Royalty is on their way to The MAJORS! @MAJORScheer í ½í²œ #MediumCoed #United"

[[5]]
[1] "charliedelmar15: I hope Reus goes to Madrid just so Hummels will be down to leave too í ½í¹\u008f #United"

[[6]]
[1] "kristian_ricky: #kostum #futsal #Mahanaim #United #MU #cup #sinode #gkj #7 #kr [pic] â€” https://t.co/BLFexQcX9Y"


[[1]]
[1] "GigaTools: DJ Soulninja is playing @ #Zero Gravity #Dubai #United Arab Emirates, Thu 22 Jan 2015 @ 21:00  #gigs"

[[2]]
[1] "sot_erika_13: RT @Spirit_ofTexas: Purple Royalty is on their way to The MAJORS! @MAJORScheer í ½í²œ #MediumCoed #United"

[[3]]
[1] "pdicey: https://t.co/E7fQFUFipD #everything #recycle #famousrecords #music #hiphop #united"

[[4]]
[1] "wendy_kizer: RT @Spirit_ofTexas: Purple Royalty is on their way to The MAJORS! @MAJORScheer í ½í²œ #MediumCoed #United"

[[5]]
[1] "charliedelmar15: I hope Reus goes to Madrid just so Hummels will be down to leave too í ½í¹\u008f #United"

[[6]]
[1] "kristian_ricky: #kostum #futsal #Mahanaim #United #MU #cup #sinode #gkj #7 #kr [pic] â€” https://t.co/BLFexQcX9Y"

