---
title: "Robinhood, your website is broken and it needs your attention now"
weight: 2
resources:
params:
date: 2020-10-07T20:18:53-05:00
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

![Sample imag](/static/img/login.jpeg)

Couple of issues with this:

1. Would this be the way going forward? As in, is Email code no longer supported?
2. Why is it not supported now? Is it a temporary issue in the backend?

#2 Corner case while making a Buy Order

While on the Ethereum's trading page, there is an option to place Limit or Market Orders. While trying to place a Limit order I hit into a conditional check for the input I provided.

1. Firstly, I'm not sure where this error is being caused as there is no callout.
2. Even if this was a plausible error, can it be in a more human readable format?

![Sample image](/static/img/glitch.jpeg)
