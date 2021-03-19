---
title: 'Meta-Data Security'
subtitle: 'What is meta-data and how to protect it'
date: 2020-11-04 00:00:00
description: What is meta-data? How do traditional messaging applications protect meta-data vs. how does Dead Drop do it?
featured_image: images/people_crossing.jpg
---

## What is meta-data?

Meta-data is everything other than the actual content of a message. It is
data <i>about</i> the data you are actually sending or receiving.

The meta-data of your communication can be used to map your whole social
network, analyze your habits, your schedule, your daily life,
your political affiliation, potential medical and legal problems, etc.

Protecting *only* the contents does not give you privacy
nor anonymity, it just requires the attacker to be a *little bit*
more resourceful.

## Traditional messaging services

> Most messaging services do not protect your meta-data at all!

Most messaging services only use **end-to-end encryption** to protect
the *contents* of your messages strongly. This works for the content. However,
this is equivalent to sending a *postcard* with the message written
in some secret code only the recipient knows, but writing the sender
and recipient name in the clear.

These services *need* to see the sender and 
recipient because they need to *deliver* the message to the recipient themselves.
The problem is, even if the service itself *promises* to not remember
who is talking to whom and when and how, etc., this information already
went through *the internet*. It is "out there". Anyone resourceful enough to listen *can* listen. Whether
they are legal entities, hackers, crackers, disgruntled employees, malicious attackers,
foreign or even domestic intelligence agencies, etc.

## How does Dead Drop work?

The idea is simple. Dead Drop does *not* deliver messages, therefore it doesn't need
to know the sender nor the recipient. Dead Drop is essentially a broadcast network.

This would be like a postcard where you cipher the message as before, but don't need to
write the sender nor the recipient on the card. Instead you go to a big community wall
when nobody is looking, and just put your postcard there. Everyone then just looks
at the wall and tries to decipher all the messages on the wall. The messages that someone *can*
decipher was obviously meant for them, that's how messages "find their way" to
the recipient.

Although there are a lot of technical challenges to make this happen
in a technically feasible and scalable way, this strategy does not leak *any*
meta-data at all. There is simply no meta-data available, so nothing has to be "promised",
quickly deleted or physically protected.

Also, all the postcards are the same size, and everybody posts postcards at
regular intervals, even if they
have nothing to say, in which case they just post some gibberish. With these
constraints, Dead Drop arrives at a unique trade-off:

> In Dead Drop nobody knows whether even a single person is communicating.

That includes the Dead Drop servers, our staff, our Hosting Provider, etc. The only
two people who even know of the *existence* of a message is the sender and the
recipient of that message.

Even if we provide our service for a 100 years and log each bit of information
our servers send and receive, at the end of the 100 years we couldn't even tell
**whether even a single message was exchanged** during those 100 years.

<!--
<span>Photo by <a href="https://unsplash.com/@ryoji__iwata?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Ryoji Iwata</a> on <a href="https://unsplash.com/s/photos/people?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
-->

