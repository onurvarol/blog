---
layout: post
title: How Twitter suspended my account
excerpt: Twitter suspended my personal account that I also use to collect dataset for my research. I am sharing my experience and some suggestions for better execution of this process.
date: 2015-08-22 22:00:00
---

It is difficult and heart-breaking for me to accept the fact that Twitter suspended [my account](https://twitter.com/onurvarol).
It felt like I did something terribly wrong.
I am not a [social bot](http://www.nasdaq.com/article/twitter-bot-scandal-puts-further-pressure-on-ceo-jack-dorsey-cm763217),
[terrorist recruiter](http://www.dailymail.co.uk/news/article-4532662/ISIS-fans-celebrate-Manchester-terror-attack.html), or an account disseminating
[hate speech](http://www.huffingtonpost.com/entry/twitter-faces-hate-speech-backlash_us_5992f62ee4b0caa1687a6383),
racist comments, and fake news. Those are the subjects that I am working on as a researcher.

This is the view of my account when it was accused of being a violator of Twitter's rules. It's also funny because I was just [talking]((https://news.northeastern.edu/2017/08/spotting-a-social-bot-might-be-harder-than-you-think/)) about Twitter's suspension policy couple of days ago. They wrote _"Identifying sophisticated bots in a systematic way has proven difficult, which is part of the reason why Twitter hasn’t done more to crack down on fake accounts. If the platform makes a mistake and suspends or bans a real person, it would be like a store wrongly accusing a customer of stealing. The ordeal might be more trouble than it’s worth."_

<div style="text-align:center; width=100%;"><img src="{{ site.baseurl }}/images/twitter-suspension/picture1.png"></div>

# Why I got banned?

As a part of my research as my other colleagues, I have been using Twitter's StreamingAPI to collect tweets based on hashtags and phrases or tracking group of users over time. I created several application keys for different purposes before. I believe this was the definition of Twitter's _multiple or repeat violations_ to suspend my account.

I would like to hear at least a notice or to get a chance to delete those applications before they suspended my account. Twitter has a limit for the number of application keys one can create in a day. However they never mention about a limit for total number of application keys one can create.

I appealed to reopen my account, but my attempts wasn't successful. Twitter sent me an email with the text below.

```
Hello,
Your account was permanently suspended due to multiple or repeat violations of the Twitter Rules: https://twitter.com/rules.
This account will not be restored.
Please do not respond to this email as replies will not be monitored.

Thanks,
Twitter Support
```

# What could Twitter do better?

Twitter proved itself as a valuable lens to understand human and group behaviors over the years. However, they can use the data they have been collecting better to address most of the important problems of society other than focusing on only creating a business model for the advertisement.

Twitter could do so many things better than its current state. They can do better job to fight fake news, hate speech, and online manipulation. They can be more open to collaborate with researchers. They are so far only open to share their data, but it seems like this will also going to change. Twitter is promoting GNIP to sell their data. Even in the link ([https://t.co/increasedaccess](https://t.co/increasedaccess)) for researchers to request more than 3 application keys, it redirects to GNIP.

- Twitter application page for developer does not have a clean interface to delete or manage applications. When I tried to delete my old application keys, I had to do all manually one by one. I actually never bothered to do that, but I could consider if they provide better interface.

- Twitter recently announced [these](https://twittercommunity.com/t/policy-clarification-multiple-applications-for-the-same-use-case/92080) policy changes. I believe this will only promote creation of more fake accounts. What they should do is better control over applications. __One can create an application and use it for malicious purposes using the accounts of all users provide permission to the application.__ We saw examples of attacks [such as this one](https://venturebeat.com/2017/03/15/twitter-accounts-hacked-with-swastikas-and-nazi-hashtags-as-political-tensions-mount-in-europe/). They can monitor applications with `write` permissions more closely than `read` ones.

- They can design better systems to identify social bots. I think Twitter's business plan limits their interest to delete or suspend social bots.

# What I am doing now?

I created a new account after several appeal requests rejected by Twitter. You can follow me now at [@onurvarolbot](https://twitter.com/onurvarolbot) (notice the difference compared to my old account name :D).

There are several points I should make here.

- __Twitter didn't allow me to download my data from my old account__. I had to follow people that I followed previously one by one again. I would like to be able to write a script to do that. But I noticed Twitter is good at recommending people from my circle. I first used followers of @ICWSM and @IC2S2 accounts to build my initial friends list and recommendation started to improve.

- Twitter black listed my phone number and this was a challenge for me to open a new account. Luckily I used Google Voice to create a phone number which redirect to my own mobile phone. (__This could be a serious flaw for Twitter to prevent social bots.__)

- This will be a funny experiment for me to see how quickly I can recover my previous network. I might be able to claim my old Twitter handle if they delete my account or maybe they can respond my appeals positively.

- I am going to write more research papers on inefficacy of Twitter to prevent serious problems on their platform.

- I can always come by more application key when I need them. This time I learned my lesson and I will keep my personal account separate from the accounts that I use to collect data.

# In the mean while

Twitter adjusted their policy about suspended accounts. I also got more clear explanation on why my account got suspended. Here is the email that I received.

```
Hello,
Your account has been suspended because multiple applications registered to your account (or accounts) have been found in violation of the Developer Agreement and Policy, including:

Developer Agreement: Sections II.A.3, II.A.5
Developer Policy: Sections I.B.7, I.F.5.a

In order for this account to be unsuspended, you should log into the Twitter Applications Management system (https://apps.twitter.com/) and delete all but one of the applications registered to your account.

Once you have completed that action, respond to this notice indicating that you have complied, and understand the requirements in the Developer Agreement and Policy prohibiting the creation of multiple applications for the same use case.

If you believe your account has been suspended in error, or wish to provide more details about the use cases for these applications, please reply to this message.

Regards,
Twitter Platform Operations
```

This is still not clear why _multiple applications registered to your account_ become a problem now. I noticed that I had way more application keys than I imagined. I partially blame myself for this because I wrote a script couple of years ago to create application keys automatically. It would be much better, if Twitter provide a better interface to manage each applications instead of asking users to delete them one by one.

I wrote a [script](https://gist.github.com/onurvarol/d0b09fe8cb38c5aa9919cfd46ab954a9) to automatize the deletion process. However, Twitter also put a rate limit on how many application you can delete. So cleaning all the applications will take some time. Eventually, I cleaned up all my previous application keys using the script. I am now waiting for them to reopen my account.

# Last words

I really like Twitter and what they provide for research community. I hope to see a better Twitter.

I will remember the 08/16 as the they my Twitter account suspended and reborn as [@onurvarolbot](https://twitter.com/onurvarolbot) :D
