

```python
import json
from collections import Counter
```


```python
data = [json.loads(line) for line in open('hw_3_twitter.json', 'r')]
```


```python
data[0]
```




    {'created_at': 'Wed Oct 03 05:00:00 +0000 2018',
     'id': 1047350533454012417,
     'id_str': '1047350533454012417',
     'text': 'RT @ELISSEsifieds: Nothing can stop us from supporting you. When we say all the way, it will be indeed. Hello Elissesifieds Cebu. \nThank yo…',
     'source': '<a href="http://twitter.com/download/iphone" rel="nofollow">Twitter for iPhone</a>',
     'truncated': False,
     'in_reply_to_status_id': None,
     'in_reply_to_status_id_str': None,
     'in_reply_to_user_id': None,
     'in_reply_to_user_id_str': None,
     'in_reply_to_screen_name': None,
     'user': {'id': 937522240488443905,
      'id_str': '937522240488443905',
      'name': "DonnaArabe'Efieds🇸🇦",
      'screen_name': 'ArabiDonna',
      'location': 'Jubail Industrial City, Kingdo',
      'url': None,
      'description': "Don't think too hard,just have fun with it.",
      'translator_type': 'none',
      'protected': False,
      'verified': False,
      'followers_count': 104,
      'friends_count': 132,
      'listed_count': 0,
      'favourites_count': 8372,
      'statuses_count': 6896,
      'created_at': 'Mon Dec 04 03:21:35 +0000 2017',
      'utc_offset': None,
      'time_zone': None,
      'geo_enabled': False,
      'lang': 'en',
      'contributors_enabled': False,
      'is_translator': False,
      'profile_background_color': 'F5F8FA',
      'profile_background_image_url': '',
      'profile_background_image_url_https': '',
      'profile_background_tile': False,
      'profile_link_color': '1DA1F2',
      'profile_sidebar_border_color': 'C0DEED',
      'profile_sidebar_fill_color': 'DDEEF6',
      'profile_text_color': '333333',
      'profile_use_background_image': True,
      'profile_image_url': 'http://pbs.twimg.com/profile_images/1047119228942393344/Px7FPs-3_normal.jpg',
      'profile_image_url_https': 'https://pbs.twimg.com/profile_images/1047119228942393344/Px7FPs-3_normal.jpg',
      'profile_banner_url': 'https://pbs.twimg.com/profile_banners/937522240488443905/1538487685',
      'default_profile': True,
      'default_profile_image': False,
      'following': None,
      'follow_request_sent': None,
      'notifications': None},
     'geo': None,
     'coordinates': None,
     'place': None,
     'contributors': None,
     'retweeted_status': {'created_at': 'Wed Oct 03 04:56:30 +0000 2018',
      'id': 1047349651915960322,
      'id_str': '1047349651915960322',
      'text': 'Nothing can stop us from supporting you. When we say all the way, it will be indeed. Hello Elissesifieds Cebu. \nTha… https://t.co/Crn6xJlhJQ',
      'display_text_range': [0, 140],
      'source': '<a href="http://twitter.com/download/android" rel="nofollow">Twitter for Android</a>',
      'truncated': True,
      'in_reply_to_status_id': None,
      'in_reply_to_status_id_str': None,
      'in_reply_to_user_id': None,
      'in_reply_to_user_id_str': None,
      'in_reply_to_screen_name': None,
      'user': {'id': 1424795701,
       'id_str': '1424795701',
       'name': 'ELISSEsifieds OFC',
       'screen_name': 'ELISSEsifieds',
       'location': 'Followed by Elisse : 08/19/13',
       'url': 'http://Facebook.com/ELISSEsifiedOfficial',
       'description': 'OFC Fansclub of @ElisseJoson ♡ Acknowledged and Recognized by Dreamscape .  (Be ELISSEsifieds just click the link and fill:http://bit.ly/1U8V5eR )',
       'translator_type': 'none',
       'protected': False,
       'verified': False,
       'followers_count': 14110,
       'friends_count': 277,
       'listed_count': 2,
       'favourites_count': 15075,
       'statuses_count': 42618,
       'created_at': 'Mon May 13 06:39:55 +0000 2013',
       'utc_offset': None,
       'time_zone': None,
       'geo_enabled': True,
       'lang': 'en',
       'contributors_enabled': False,
       'is_translator': False,
       'profile_background_color': 'C0DEED',
       'profile_background_image_url': 'http://abs.twimg.com/images/themes/theme1/bg.png',
       'profile_background_image_url_https': 'https://abs.twimg.com/images/themes/theme1/bg.png',
       'profile_background_tile': True,
       'profile_link_color': 'F099F0',
       'profile_sidebar_border_color': 'FFFFFF',
       'profile_sidebar_fill_color': 'DDEEF6',
       'profile_text_color': '333333',
       'profile_use_background_image': True,
       'profile_image_url': 'http://pbs.twimg.com/profile_images/975532647349854209/glaBAm_T_normal.jpg',
       'profile_image_url_https': 'https://pbs.twimg.com/profile_images/975532647349854209/glaBAm_T_normal.jpg',
       'profile_banner_url': 'https://pbs.twimg.com/profile_banners/1424795701/1490279660',
       'default_profile': False,
       'default_profile_image': False,
       'following': None,
       'follow_request_sent': None,
       'notifications': None},
      'geo': None,
      'coordinates': None,
      'place': None,
      'contributors': None,
      'is_quote_status': False,
      'extended_tweet': {'full_text': 'Nothing can stop us from supporting you. When we say all the way, it will be indeed. Hello Elissesifieds Cebu. \nThank you guys, for rising so early just to visit Elisse on her last taping day sa humble place nyo💓 https://t.co/cLpJ2ifyGw',
       'display_text_range': [0, 212],
       'entities': {'hashtags': [],
        'urls': [],
        'user_mentions': [],
        'symbols': [],
        'media': [{'id': 1047349579832688641,
          'id_str': '1047349579832688641',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju5M2VAAESKaQ.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju5M2VAAESKaQ.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'large': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'}}},
         {'id': 1047349589253083136,
          'id_str': '1047349589253083136',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju5v8U0AAhr9-.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju5v8U0AAhr9-.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'}}},
         {'id': 1047349602142150657,
          'id_str': '1047349602142150657',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju6f9UYAEfHDd.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju6f9UYAEfHDd.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'}}},
         {'id': 1047349625907109889,
          'id_str': '1047349625907109889',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju74fU4AEpxTQ.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju74fU4AEpxTQ.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'}}}]},
       'extended_entities': {'media': [{'id': 1047349579832688641,
          'id_str': '1047349579832688641',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju5M2VAAESKaQ.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju5M2VAAESKaQ.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'large': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'}}},
         {'id': 1047349589253083136,
          'id_str': '1047349589253083136',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju5v8U0AAhr9-.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju5v8U0AAhr9-.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'}}},
         {'id': 1047349602142150657,
          'id_str': '1047349602142150657',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju6f9UYAEfHDd.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju6f9UYAEfHDd.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'}}},
         {'id': 1047349625907109889,
          'id_str': '1047349625907109889',
          'indices': [213, 236],
          'media_url': 'http://pbs.twimg.com/media/Doju74fU4AEpxTQ.jpg',
          'media_url_https': 'https://pbs.twimg.com/media/Doju74fU4AEpxTQ.jpg',
          'url': 'https://t.co/cLpJ2ifyGw',
          'display_url': 'pic.twitter.com/cLpJ2ifyGw',
          'expanded_url': 'https://twitter.com/ELISSEsifieds/status/1047349651915960322/photo/1',
          'type': 'photo',
          'sizes': {'thumb': {'w': 150, 'h': 150, 'resize': 'crop'},
           'medium': {'w': 720, 'h': 960, 'resize': 'fit'},
           'small': {'w': 510, 'h': 680, 'resize': 'fit'},
           'large': {'w': 720, 'h': 960, 'resize': 'fit'}}}]}},
      'quote_count': 0,
      'reply_count': 0,
      'retweet_count': 3,
      'favorite_count': 9,
      'entities': {'hashtags': [],
       'urls': [{'url': 'https://t.co/Crn6xJlhJQ',
         'expanded_url': 'https://twitter.com/i/web/status/1047349651915960322',
         'display_url': 'twitter.com/i/web/status/1…',
         'indices': [117, 140]}],
       'user_mentions': [],
       'symbols': []},
      'favorited': False,
      'retweeted': False,
      'possibly_sensitive': False,
      'filter_level': 'low',
      'lang': 'en'},
     'is_quote_status': False,
     'quote_count': 0,
     'reply_count': 0,
     'retweet_count': 0,
     'favorite_count': 0,
     'entities': {'hashtags': [],
      'urls': [],
      'user_mentions': [{'screen_name': 'ELISSEsifieds',
        'name': 'ELISSEsifieds OFC',
        'id': 1424795701,
        'id_str': '1424795701',
        'indices': [3, 17]}],
      'symbols': []},
     'favorited': False,
     'retweeted': False,
     'filter_level': 'low',
     'lang': 'en',
     'timestamp_ms': '1538542800664'}




```python
len(data)
```




    2556




```python
sum('delete' in t for t in data)/len(data)
```




    0.14162754303599373




```python
langs = [t['lang'] for t in data if 'lang' in t]
```


```python
Counter(langs).most_common(10)
```




    [('en', 719),
     ('ja', 438),
     ('es', 173),
     ('ko', 149),
     ('th', 123),
     ('ar', 119),
     ('und', 117),
     ('in', 71),
     ('pt', 69),
     ('fr', 35)]




```python
cnt = Counter([t['user']['id'] for t in data if 'user' in t])
```


```python
for key in sorted(cnt, key=cnt.get, reverse=True):
    if cnt[key] > 1:
        print(cnt[key], key)
```

    2 992084216350294016
    2 581282101
    2 2317193324
    2 978499715657445377
    2 2245928100
    2 993031040
    2 290401936
    2 3067130479
    2 849417895109156869
    2 958056194366754816
    2 1017442172495331328
    2 702487896935104513
    2 995683537197158401
    2 121016179
    2 947288315375394817
    2 2464271844
    2 1009443285176340482
    2 860202971266772992
    2 2734975298
    2 4311188534
    2 1290792062
    2 897067178754686976
    2 4179415159
    2 772081812109570048
    2 1006114081739288577
    


```python
hashtags = []
for t in data:
    if 'entities' in t:
        if 'hashtags' in t['entities'] and t['entities']['hashtags']:
            hashtags.extend([i['text'] for i in t['entities']['hashtags']])
```


```python
Counter(hashtags).most_common(20)
```




    [('BTS', 17),
     ('방탄소년단', 13),
     ('AMAs', 11),
     ('人気投票ガチャ', 8),
     ('태형', 7),
     ('뷔', 6),
     ('BTSinChicago', 5),
     ('BTSLoveYourselfTour', 5),
     ('오늘의방탄', 5),
     ('PledgeForSwachhBharat', 5),
     ('MPN', 5),
     ('PCAs', 4),
     ('V', 4),
     ('시카고1회차공연', 4),
     ('เป๊กผลิตโชค', 4),
     ('JIMIN', 4),
     ('running', 3),
     ('NCT', 3),
     ('지민', 3),
     ('WajahmuPlastik', 3)]




```python
from string import punctuation

```


```python
texts = []
for t in data:
    if 'retweeted_status' in t:
        pass
    elif 'text' in t and t['lang'] == 'en':
        texts.append(' '.join([w.strip(punctuation) for w in t['text'].lower().split()]))

all_tweets = ' '.join(texts)
d = Counter(all_tweets.split())
```


```python
d.most_common(25)
```




    [('the', 125),
     ('to', 86),
     ('a', 75),
     ('i', 73),
     ('and', 64),
     ('is', 50),
     ('you', 48),
     ('of', 45),
     ('for', 42),
     ('it', 41),
     ('in', 38),
     ('that', 33),
     ('this', 31),
     ('my', 30),
     ('me', 27),
     ('be', 26),
     ('on', 26),
     ('are', 21),
     ('what', 20),
     ('so', 20),
     ('with', 20),
     ('have', 19),
     ('not', 17),
     ('more', 17),
     ('but', 17)]




```python
d = {}
for t in data:
    if 'user' in t:
        d[t['user']['name']] = t['user']['followers_count']
```


```python
for key in sorted(d, key=d.get, reverse=True)[:10]:
    print(d[key], key)
```

    2521403 Filosofía♕
    1491309 FITNESS Magazine
    1206759 malaysiakini.com
    1137374 NYT Science
    625463 Gramática
    392472 TGRT Haber
    383698 The Sun Football ⚽
    374222 Melbourne, Australia
    318189 Roznama Express
    311319 💞 ცųཞɠɛཞცơơɠıɛ 💞
    


```python
import re

reg = re.compile('^.*?>(.*?)<.*?$')

sources = []
for t in data:
    if 'source' in t:
        res = reg.findall(t['source'])
        if res:
            sources.extend(res)
```


```python
Counter(sources).most_common(20)
```




    [('Twitter for iPhone', 800),
     ('Twitter for Android', 695),
     ('Twitter Web Client', 140),
     ('twittbot.net', 122),
     ('Twitter Lite', 51),
     ('Twitter for iPad', 28),
     ('TweetDeck', 23),
     ('Facebook', 17),
     ('IFTTT', 14),
     ('تطبيق قرآني', 10),
     ('dlvr.it', 10),
     ('Buffer', 8),
     ('Google', 8),
     ('autotweety.net', 7),
     ('Hootsuite Inc.', 7),
     ('WordPress.com', 6),
     ('Twittascope', 6),
     ('Botbird tweets', 6),
     ('تطبيق دعـاء', 5),
     ('Zapier.com', 5)]


