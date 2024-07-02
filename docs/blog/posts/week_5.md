---
date: 2024-06-28
categories: [Internship]
authors: [nangosha]
draft: true
---

# Week 5: How to add analytics to a website

This week, we shall have an introduction at site analytics, basic terminologies and concepts. In the end we shall look at how to add Google analytics to our site

<!-- more -->
![Analytics dashboard](image-7.png)

## Why are we even interested in analytics? 
- Analytics helps you understand how people use your sites and apps, so you can take action to improve their experience.

## What are the possible approaches to analytics?

## What are the key  metrics for Google analytics(what are we looking for)?

- Bounce rate - These are the number of people who leave a site without taking any action i.e. they come, they go!
 A bounce is when someone lands on your site and then leaves from that same page. This is a sign that though the ad or marketing efforts got them there, they weren’t engaged enough to stay.

- Traffic by source - Where did this user come from - was it a link, direct typing of URL, marketing etc.
Other common sources of traffic include organic search, social media, email marketing, and paid advertising.

- Conversion rate - This indicates whether a user completed the intended action on the page e.g. registering for a newsletter, signing up etc. This is normally a percentage!

- Average time on page - This shows the average time that a user spends on a single page

- Page loading time - This is exactly what it says!

- Site visitors - This is the quantity of traffic your site gets in a given period. It could give an idea of the reach of your site.

- Unique visitors - The number of people visiting your site for the first time.


## Why would you want a Google analytics alternative

Here are some reasons why you would want to look into an alternative service

## Here are some alternatives to Google analytics
- Matomo analytics
- Adobe analytics
- plausible analytics
- semrush
- simple analytics

## Add Google analytics to your site

For this blog, I will be adding analytics to this very blog site that you are viewing right now

1. **Create an analytics account**: If you have a Google account, then you are most likely good to go. It could be the case though that you have many seperate apps/websites that you like to track. Or it could so happen that you want to use seperate accounts for say both work and personal. If that's so, then you can proceed to create another account.

Here is a sample image from the `Create account screen`
![Create analytics account](image-8.png)

2. After you create an account, proceed to create a `property`
3. Proceed to describe your business details on the next page
4. On the next page, select how you intend to use Google analytics. In my case, I will just click `Examine user behavior` since it looks more fitting. Actually, I will also click `Generate leads` because why not??
![Choose business objectives](image-9.png)
5. Click `Create` to finish creating the property
6. To start collecting our data, let's choose a platform in our case `web`
![Start collecting data](image-10.png)
7. Enter the url of your primary website, in my case `trevor-james-nangosha.github.io`. Give your stream a name. Click `Create stream`


## Some key concepts to note:

- Properties

## Important links for further reading

- https://support.google.com/analytics/answer/9304153?hl=en

<!-- 

Google tag (gtag.js)
<script async src="https://www.googletagmanager.com/gtag/js?id=G-GNG4PJ8C5Z"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-GNG4PJ8C5Z');
</script>

 -->
