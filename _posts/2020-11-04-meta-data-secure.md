---
title: 'Meta-Data Security'
subtitle: 'Why meta-data should matter to everybody'
date: 2020-11-04 00:00:00
description: What is meta-data and more importantly what is its value? How does Dead Drop compare to other services in protecting users' meta-data?
featured_image: images/people_crossing.jpg
---

## What is meta-data?

In short, meta-data is everything other than the actual content of the message. It is
data <i>about</i> the data you are actually sending or receiving.

Here are just some things this includes:

* <b>Size of the message</b>. How long the text is, how large the image or video.
* The type and <b>composition of the message</b>. Is it a text message, does it contain images, videos, audio, etc.
* <b>Time</b> of sending and receiving.
* <b>Parties involved</b> in the message. Who sent it, who received it, whether there were multiple recipients and who those were.

The <i>continuous</i> monitoring of such meta-data over time may lead to additional information such as:

* With what frequency are two parties communicating. Daily, weekly, etc.?
* Do parties lead conversations, or is the communication one way?
* With what real-world events are these communications correlated?
* What is the <b>social network</b> of any given individual he/she often communicates with. This includes people, companies, political parties, people with certain professions, etc.

## How valuable is it?

According to some experts[^1] meta-data is at least as valuable, and in certain instances
can be <i>more</i> valuable than the content itself.

It is not hard to imagine[^2] that contacting a specialist doctor, a lawyer specializing on a certain
field of law, or an investigative journalist <i>itself</i> can tell the whole story about a situation,
without looking at the contents of those communications.

Also revealing is the fact that law enforcement agencies and governments around the world
<i>want</i> communication meta-data collection[^3][^4][^5][^6].

## How do other communication apps protect meta-data?

Most, even those with end-to-end encryption, simply don't protect meta-data at all! All of the
information above is available and goes over the public internet unprotected.

Some services do promise that they immediately delete the data or that they don't keep
records. Even if that were the case, that information already went through the whole internet 
infrastructure, was on their servers, however briefly, and then got deleted.

It is pretty clear that this level of "protection" is inadequate even if you trust the service. Here
are some reasons why:

* What about third parties <i>listening</i> or <i>logging</i>, not the service itself?
* What about hackers/crackers that have access to their servers.
* What about disgruntled employees having access to their servers.
* What about <i>legal</i> access that <i>need</i> to be provided to law enforcement in some jurisdictions?
* What about potential laws now <i>or in the future</i> that <i>require</i> some information to be kept?
* What about attackers of <i>any</i> internet infrastructure between the service's servers and the user?
* What about <i>legal</i> data surveillance at the internet service provider (ISP) level?
* ...and so on...

The only service that at least <i>tries</i> to address these issues is Tor[^7]. But instead of strongly protecting
meta-data, it tries to statistically <i>mask</i> it, which still leaves it partially open to different categories 
of statistical analysis[^8].

## How does Dead Drop protect meta-data?

Dead Drop is designed to have <b>zero information</b> not only about the contents of a message
but also the meta-data of the message. The <i>routing information</i> that causes the problems
for other services does not reach our servers, nor does it go through the internet. It simply
does not exists!

How is that possible? It is simple really. Dead Drop is essentially a <i>broadcast</i> network. Everyone can
hear everyone else, so there is no need for <i>routing</i>. No need for an <i>envelope</i> where the
sender and recipient needs to be named. A Dead Drop app essentially just listens to everybody and <i>selects</i> the
messages it can decrypt with its own keys. And because everyone in the Dead Drop network is <i>talking constantly</i>
at the <i>exact same rate</i> it is impossible to know who is talking to whom, or even <b>who is talking at all</b>.

This level of protection requires a trade-off however. Currently the
Dead Drop app can only send and receive one text message per hour with a maximum of 10KB each. These limits
are technical in nature and balance network usage, server resource usage and usability.

For situations where complete anonymity and privacy is of utmost importance even against
powerful attackers with vast network surveillance and statistical computation capabilities,
this is the trade-off that <i>has</i> to be made.

[^1]: [Can Snowden finally kill the 'harmless metadata' myth?](https://www.zdnet.com/article/can-snowden-finally-kill-the-harmless-metadata-myth/)
[^2]: [Here’s how phone metadata can reveal your affairs, abortions, and other secrets](https://www.washingtonpost.com/news/the-switch/wp/2013/08/27/heres-how-phone-metadata-can-reveal-your-affairs-abortions-and-other-secrets/)
[^3]: [What’s the Matter with Metadata?](https://www.newyorker.com/news/news-desk/whats-the-matter-with-metadata)
[^4]: [Why Metadata Matters: The Dangers and Revealing Nature of Data Retention](https://www.eff.org/node/81907)
[^5]: [PRISM](https://en.wikipedia.org/wiki/PRISM_(surveillance_program))
[^6]: [New German law would force ISPs to allow secret service to install trojans on user devices](https://www.privateinternetaccess.com/blog/new-german-law-would-force-isps-to-allow-secret-service-to-install-trojans-on-user-devices/)
[^7]: [Tor Project](https://www.torproject.org/)
[^8]: [Darknet Security: A Categorization of Attacks to the Tor Network](http://ceur-ws.org/Vol-2315/paper10.pdf)

<!--
<span>Photo by <a href="https://unsplash.com/@ryoji__iwata?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Ryoji Iwata</a> on <a href="https://unsplash.com/s/photos/people?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
-->

