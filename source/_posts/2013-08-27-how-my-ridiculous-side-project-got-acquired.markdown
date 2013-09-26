---
layout: post
title: "My side project got acquired - lessons learned"
date: 2013-08-27 22:03
comments: true
categories:
published: false
---

The story of my side project starts in May 2012 as a tired cliche: a programmer in a coffee shop on his MacBook Air.

Earlier that week, [Planetary Resources](http://www.planetaryresources.com/) had [announced](http://www.space.com/15395-asteroid-mining-planetary-resources.html) its intent to mine water and valuable materials from asteroids.  Like many others, I was intrigued.  It was a bold, impossible startup that had long-term vision and pushed a lot of boundaries.

[Asterank](http://asterank.com) began as a thought experiment: how much are asteroids really worth?  The media was publishing wild estimates without any scientific basis.  No one was actually doing the math.

[{% imgcap center http://i.imgur.com/Lxw7Ffqm.jpg %}](http://asterank.com)

13 months later, when Asterank was acquired by Planetary Resources, it was much more than an asteroid value calculator.  It was a full astronomical toolkit that included web scrapers, a data pipeline, powerful visualizations, and the ability to discover new asteroids.

**I had no idea what I was doing.**  I still don't.  But here are some lessons I've learned along the way:

## Lesson 1: Bug people

I contacted many people who could help me materially or by critiquing my project.

The key is being patient and not coming off as desperate.  Follow up every two weeks if you've had near-term contact, one month if you haven't.

### Cold email guidelines

Here's how I initially contacted people:

  * Briefly describe what I made and the success I've already had (# visitors, news coverage, etc.).
  * Tell them what my goal is.
  * Ask them for something that will help me accomplish this goal.

This shouldn't take more than 2 or 3 short paragraphs.  Follow-up emails should be even shorter:

  * Update on project - latest successes, features, etc. (skip this if you're following up on a promise they've already made).
  * Ask them for something.

### Choosing the victims

Here are some of the people I emailed regularly:

  * my contact at Planetary Resources.
  * contacts at many other space companies.
  * scientists at prestigious institutions.
  * space bloggers.
  * the professor who taught my 100-person Intro to Astronomy course.

Most of your emails won't get read.  This can be insulting and stressful.  Hang in there and take nothing personally.

[Boomerang for Gmail](http://www.boomeranggmail.com/) is a great tool for email reminders.  I used the free version and followed up once a month with people I was interested in.

{% img center http://i.imgur.com/Y7woyuB.png?1 %}

Over time, people started initiating contact instead of the other way around, and my network grew.  Persistent emails were the single largest contributing factor in the success of Asterank.

## Lesson 2: Viral/social content is unpredictable

When I launched, the only self-promotion I did was a [Hacker News post](https://news.ycombinator.com/item?id=3967670), which gained a total of 2 points (I deserved this for giving it such an awful linkbait title).

Fortunately, someone picked it up and Asterank was featured on [Universe Today](http://www.universetoday.com/95169/the-most-profitable-asteroid-is/), a popular space blog.  A couple people including the Planetary Resources leadership contacted me afterwards.  From then on, traffic was steady but with major spikes from aggregators, news coverage, etc.

{% imgcap center http://i.imgur.com/hfG0gnH.png Merry Christmas - the site is down. %}

Did you know you can "submit" to HN as many times as you want?  If no one is interested in your project, just blog about it until they notice it.  I posted [Asterank Discover](http://asterank.com/discover) on HN and it got 5 points.  I wrote a [blog post](www.ianww.com/blog/2013/08/05/how-a-programmer-can-discover-an-asteroid/) about it that made the front page.  Go figure.

Caveat: social traffic fades quickly and is mostly full of people who are not that interested in what you're making.  It was helpful in getting started, but the results were not permanent and the marginal benefit decreases quickly.

## Lesson 3: Giving feedback on your site should be very easy

Some of my best contacts who contributed significantly to the project came through Asterank's About/Feedback page.  I provided my email address and added a contact form.  People tend to prefer the form, but I recommend having both (the form is low-friction, but people who want to speak directly prefer email).

{% imgcap center http://i.imgur.com/FTOZyrJm.png A basic email form takes a few minutes to add but is extremely valuable. %}

I also added a way to "subscribe to updates," but it actually just sent me their email address.  I used this to gage interest; there was no point in setting up a mailing list before I knew people would use it.

Regardless of how you want to be contacted, an easy-to-find About page is essential.  It facilitated several job opportunities, conference invitiations, and media interview requests.

## Lesson 4: LinkedIn can sometimes be useful

LinkedIn is full of bullshit, but most people are on it.  This is especially useful if you're tackling something outside tech.  It allowed the Planetary Resources guys to find me initially.

{% imgcap center http://i.imgur.com/LtfZbIxm.png I am thankful for gmail filters. %}

Many software engineers I know question the value of LinkedIn.  It may cost you some sanity, but maintaining a basic, up-to-date profile was worth it.

## Lesson 5: Open source everything you can

Most people are surprised when I tell them Asterank is entirely [open source](https://github.com/typpo/asterank).  It lends an air of transparency and invites collaborators.  The project is better off for it.

Most people who said they wanted to participate never actually contributed, but they had valuable ideas.  Open sourcing was a great way to meet people who wanted to support and innovate the project.

## Lesson 6: There might be leads in your analytics

Scan your analytics every now and then, especially referers.  I made a valuable contact just by noticing a link from company email.  I reached out without referencing that I was watching the logs, but it's much easier to "cold" contact someone you know is already interested.

When I sent emails, I sometimes tracked clicks by linking `http://asterank.com/?f=n`, where n is a unique string.  This way, even if they didn't respond, I could tell who was interested enough to click.

## Lesson 8: Stick with it

I have 5+ side projects. I feel some of them could be businesses, but I always get bored after a couple weeks.  Asterank was the only side project that I've stuck with for over a year, and it paid off even though it could never really be monetized.

{% imgcap center http://i.imgur.com/PSu18sK.png Maybe I should get out more. %}

## Be grateful

I had to make some hard decisions and turn down some great opportunities to wind up here.  I'm really lucky to have had those options.

I'm excited to learn and see where this takes me.

Good luck!
