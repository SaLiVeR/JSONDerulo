# JSONDerulo - A JSON feed fetcher for MODX Revolution CMS

## Available snippets

### App.net

You need your user id to get this working, not your username. You can find it on your profile page. [Hat tip to "man"](https://alpha.app.net/man/post/20858).

```
<ul>
    [[!JSONDerulo?
        &feed=`appnet`
        &tpl=`jd.appNet`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE` &userId=`USERID`
    ]]
</ul>
```

### Delicious

```
<ul>
    [[!JSONDerulo?
        &feed=`delicious`
        &tpl=`jd.delicious`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE` &users=`USERNAME`
    ]]
</ul>
```

### Flickr

Requires API key, get one here: [Flickr API Key](http://www.flickr.com/services/apps/create/apply)

```
<ul>
    [[!JSONDerulo?
        &feed=`flickr`
        &tpl=`jd.flickr`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`FLICKR USER ID`
        &apiKey=`API_KEY`
        &userName=`USERNAME`
    ]]
</ul>
```

### Google+

Requires API key, get one here: [Google API key](https://code.google.com/apis/console/)

```
<ul>
    [[!JSONDerulo?
        &feed=`googleplus`
        &tpl=`jd.googlePlus`
        &limit=`LIMIT`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &userId=`USER_ID`
        &apiKey=`API_KEY`
    ]]
</ul>
```

### Google calendar

You'll need to find the calendar's public feed URL. Don't panic, [read the instructions further down the page](#google-calendar-and-public-feed-urls)...

```
<ul>
    [[!JSONDerulo?
        &feed=`googlecalendar`
        &tpl=`jd.googleCalendar`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &feedLocation=`FEED LOCATION`
    ]]
</ul>
```

### LastFM

Requires api key, get one here: [LastFM API Key](http://www.last.fm/api/account)

```
<ul>
    [[!JSONDerulo?
        &feed=`lastfm`
        &tpl=`jd.lastFm`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERNAME`
        &apiKey=`API KEY`
    ]]
</ul>
```

```
<ul>
    [[!JSONDerulo?
        &feed=`lastfmlistens`
        &tpl=`jd.lastFm`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERNAME`
        &apiKey=`API KEY`
    ]]
</ul>
```

### Picasa

```
<ul>
    [[!JSONDerulo?
        &feed=`picasa`
        &tpl=`jd.picasa`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERID`
        &albumId=`ALBUMID`
        &albumName=`ALBUMNAME`
    ]]
</ul>
```

### Tumblr

The &postType option is optional (if not set, feed will return all post types), but can be set to ```audio```, ```video```, ```photo```, ```link```, ```text```

You can only set ONE postType.

```
<ul>
    [[!JSONDerulo?
        &feed=`tumblr`
        &tpl=`jd.tumblr`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &tag=`TAG TO FILTER BY`
        &postType=`POST TYPE TO FETCH`
        &notesInfo=`TRUE or FALSE`
        &blogUrl=`YOUR TUMBLR URL`
        &apiKey=`API KEY`
    ]]
</ul>
```

### Twitter

You need to set up a Twitter "App" to make this work - [from here](https://dev.twitter.com/apps). From March 2013, this is the ONLY way.

The cacheName option is for users who may want to use the snippet more than once on a site for different users' tweets. Setting this appends the text to the cache filename so multiple feeds can be cached. I've added a string replacement to swap spaces for hyphens in there too.

The screenName option is *optional*. It will allow you to fetch another user's timeline. If this is not provided, it will default to the user whose consumer key, etc, that you are using.

```
<ul>
    [[!JSONDerulo?
        &feed=`twitter`
        &tpl=`jd.twitter`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_TO_APPEND_TO_CACHE_FILE`
        &screenName=`USER_SCREEN_NAME_TO_FETCH_TIMELINE_FOR`
        &includeRTs=`1 or 0`
        &consumerKey=`YOUR_CONSUMER_KEY`
        &consumerSecret=`YOUR_CONSUMER_SECRET`
        &accessToken=`YOUR_ACCESS_TOKEN`
        &accessTokenSecret=`YOUR_ACCESS_TOKEN_SECRET`
    ]]
</ul>
```

### Vimeo

```
<ul>
    [[!JSONDerulo?
        &feed=`vimeo`
        &tpl=`jd.vimeo`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERNAME`
    ]]
</ul>
```

### YouTube

```
<ul>
    [[!JSONDerulo?
        &feed=`youtubev2`
        &tpl=`jd.youTube`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERNAME`
    ]]
</ul>
```

```
<ul>
    [[!JSONDerulo?
        &feed=`youtubev2uploads`
        &tpl=`jd.youTube`
        &limit=`LIMIT`
        &users=`USERNAME`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
    ]]
</ul>
```

```
<ul>
    [[!JSONDerulo?
        &feed=`youtubev3playlist`
        &tpl=`jd.youTube`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &apiKey=`YOUR_V3_API_KEY`
        &playlistId=`YOUR_PLAYLIST_ID`
    ]]
</ul>
```

Grab an API key for v3 from [Google API Console](https://code.google.com/apis/console/). Ensure you switch API v3 access on!

### ZooTool

Requires API key, get one here: [ZooTool API Key](http://zootool.com/api/keys)

```
<ul>
    [[!JSONDerulo?
        &feed=`zootool`
        &tpl=`jd.zooTool`
        &limit=`LIMIT`
        &cacheTime=`CACHE_TIME_IN_SECONDS`
        &cacheName=`UNIQUE_NAME_FOR_CACHE_FILE`
        &users=`USERNAME`
        &apiKey=`API KEY`
    ]]
</ul>
```
