---
layout: post
title: "Mint is misleading users about heartbleed (and may still be vulnerable)"
date: 2014-04-15 10:31
comments: true
categories:
---

**Update** *April 15, 2014: Mint followed up and made a clear statement that the site has never used a version of OpenSSL vulnerable to Heartbleed.  This is great news.  Hopefully in the future Mint will move quickly and definitively to address security concerns.*

[Mint.com](http://mint.com) is a popular personal finance site used by over 10 million people.  Users enter bank logins and Mint aggregates everything so you can see your financials in one place.

When I heard about the [Heartbleed](http://heartbleed.com) vulnerability, I immediately thought of Mint.  They have all my financial logins and sensitive information.  All my bank information is potentially compromised.

Unfortunately, Mint has bungled their response to the Heartbleed and may still be exposing users to attack.

<!-- more -->

## April 9th: Mint confirms vulnerability

Heartbleed became public on April 7th.  Mint made no official statement, but on April 8th someone [asked](https://satisfaction.mint.com/mint/topics/is_mint_com_secured_and_recovered_from_the_heartbleed_bug) on their public support forums whether the site was vulnerable.

Two days after most of the internet found out about Heartbleed, a Mint representative apologized for the delay and replied:

{% img center http://i.imgur.com/PQX5PHt.png Mint's official response to Heartbleed. %}

Jami's post, stating that the team was "**upgrading to protect against the vulnerability**," is a strong indication that Mint was vulnerable to Heartbleed.

### Mint's old cert

After confirming that the vulnerability was patched, people noticed that Mint is still using an SSL certificate from February.  This means that attackers can pose as Mint and any "secure" connection to Mint still cannot be trusted.

As a result, users continued to complain that Mint is still vulnerable to Heartbleed-related security problems.

## April 10th: Mint is no longer vulnerable?

The next day, Mint made a reply that puzzled everyone:

{% img center http://i.imgur.com/Cqufo45.png %}

Mint is "not affected" by Heartbleed and we have nothing to worry about.

This post was extremely unhelpful.  Of course Mint is not affected post-fix.  The question is, was it affected during the 2 years the vulnerability was in the wild?

## Mint's contradictory statements

Jami's 2 and 3-sentence responses are all we got from Mint, a financial service with information on over 17 million financial accounts.  Unfortunately, the posts contradict one another and both cannot be true.

### Possibility 1: Mint's first post is true

The first official response states that engineers are taking action by applying server upgrades to fix the vulnerability.

In other words, Mint was vulnerable.  But because the site is using an old certificate, **it is still not safe to use Mint.com**.  Over a week after the vulnerability became public, all Mint.com users are at risk.

### Possibility 2: Mint's second post is true

The second official response states that "Mint is not affected" and we have nothing to worry about.

If we interpret the second post generously and assume Mint was *never* affected, the first official statement is false or at best ambiguous.  What does it means to update servers "to protect against the vulnerability" if it was never a problem?

On the other hand, if the vulnerability existed and was closed, someone at Mint doesn't understand the vulnerability and the need to change SSL certificates.  In other words, one of the world's largest online finance tools is still vulnerable.

## A lesson learned

I need to change my financial passwords regardless.  But it's been over a week and I still can't trust my Mint login.  Even once it's fixed, do I want to use a finance site that does not take security seriously and cannot issue a coherent statement to address one of the largest security holes in history?

{% imgcap center http://i.imgur.com/z2E6wxk.png LastPass agrees - Mint may still be vulnerable %}

Predictably, the remainder of the support thread is people trying to reconcile Mint's responses.  Some assume the worst, some give Mint the benefit of the doubt.  The analysis is completely open to interpretation.

**Mint, your two short replies to the largest security vulnerability ever fundamentally contradict one another.**

A company that handles sensitive financial information needs to communicate security clearly and effectively.  Otherwise, users can't trust the service.  Mint owes its users an official, unambiguous technical statement.
