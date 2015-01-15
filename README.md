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
  > library(twitteR)
3- Download the curl certificate needed for twitter authentication
  > download.file(url="http://curl.haxx.se/ca/cacert.pem", destfile="cacert.pem")
4- Set the twitter certificate
  > 
