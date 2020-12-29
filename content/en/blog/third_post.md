---
title: "Robinhood, your website is broken and it needs your attention now"
weight: 2
resources:
params:
date: 2020-12-22T20:18:53-05:00
showDate: false
draft: false
tags: ["blog","product"]
---


Hitting into live bugs ignites my left brain at that very moment. Soon a series of rabbit hole explorations ensue, root causing it while I go about my original task. When I ruminate on it a bit later I come up with proposals to resolve and make things better. Giving my right brain its share of work. Here's something I've bumped into:

Robinhood's mobile app has unlocked a power user group — millennials. More so that institutional investors start to pause and take a look at this new phenomenon transpiring in the markets today. Robinhood has made this experience easier while gamifying it for the newcomers to the world of investing/trading - not just traditional finance but crypto as well.

With all this heavy usage on the mobile platform, I would consider the downtime and reliability to be prime focus because everybody has right to their accounts and money at any point of time. This is true irrespective of the platform - mobile/web. Heavy usage can also be attributed partly to the crypto cycle we're in. There is lot of focus followed by demand on the cryptocurrencies. Robinhood supports a limited number of cryptocurrencies on its platform. 

Quite often I logon to the web interface to analyze the charts on my bigger screen while having dedicated tabs for this purpose on my browser. While I was going about my activities this time I hit into a UI/infra bug and a process/product bug. 

Let me talk about the product bug and then we can look at the infra bug because I've identified the issues in this order during my journey.

#1 Sign in process - 2FA

Robinhood provides an opportunity to 2FA using Text or Email but once I select Email I get an error stating 'Email code is no longer supported. Please request SMS code sent to your phone number.'

![Sample imag](/blog/login.jpeg "Sign-in 2FA page")

Couple of issues with this:

1. Would this be the way going forward? As in, is Email code no longer supported?
2. Why is it not supported now? Is it a temporary issue in the backend?

#2 Corner case while making a Buy Order

While on the Ethereum's trading page, there is an option to place Limit or Market Orders. While trying to place a Limit order I hit into a conditional check for the input I provided.

1. Firstly, I'm not sure where this error is being caused as there is no callout.
2. Even if this was a plausible error, can it be in a more human readable format?

![Sample image](/blog/glitch.jpeg "Textbox error")

![Sample gif](/img/screencap.gif.gif)

Solution
------
Currently, the sign in process on web seems to be supporting only Text 2FA. Which is still fine as long as the user experience is addressed. If the user requests Email 2FA the page just returns an Error which is not intuitive. 

In order to go forward with a solution, need to figure roadmap for 2FA. Should 2FA support both text and email? Once this is clear, the use case will be clear resulting in either bringing back text 2FA  support or updating UI to reflect roadmap.

As to the Error/bug in the box, rigorous testing on production needs to be in place. Taking into account various possible edge cases. 

Feedback for future issues

Given issues and bugs like this are inevitable, a solid pipeline can help identify, root-cause and fix things soon. I tried to look up the existing mechanism in place for reporting issues/feedback. There are 2 places I looked at: Help Center and Support. Help Center has indexed pre-written content. I couldn't find anything on the issues I faced. So, next was to look at Support page. This page provided dropdown menus to narrow down the context and subsequently report the feedback or issue. 

While rummaging within these drop-down menus, I couldn't find any closest category. Then I went ahead selecting 'Other' categories and reached a page which provided an Email feedback textbox. But, I was unsure how this textual description could be helpful or spot-on for abstract situations like the issue I faced. Even avid users might just drop out somewhere in this pipeline failing to provide constructive feedback.

I then looked at how some of the competition is taking care of this feedback loop. Another service I use is E*trade. Even though its not a direct competitor, E*trade has a full-fledged customer support page with live chat. My experience with that live chat was not a breeze as it took around ~45 minute wait. Nevertheless, providing customer support with live chat is a solid system but needs lot of resources. 

Robinhood would definitely benefit by developing a customer support platform which is live, in the long term. But, couple of good starting points in the short-term would be 

#1 Provided a way to attach images in feedback

#2 Providing in-line feedback

Providing a way to attach images should help with majority of the problems - categorized and non-categorized. While being just a small enhancement over the existing infrastructure. Most of platforms today also support in-line feedback while this has its own pros and cons, needs further deliberation and changes on the platform to implement.

___
To Robinhood, I hope my brainstorming in this blog post; with proposals to fix the user experience, can be received as direct feedback.
