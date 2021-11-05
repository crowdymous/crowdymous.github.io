---
title: 'Untraceable Communication is Here'
subtitle: 'Digital Spycraft'
date: 2021-10-29 00:00:00
description: Spies have been using physical "Dead Drops" to exchange information securely for decades. This method has now become digital and accessible to everyone.
featured_image: images/phone_user.jpg
---

Have you ever watched a spy movie where the hero causally walks to a bench in a park
and nonchalantly retrieves some papers from under it, or a microfilm roll, or in a more modern spy movie an sd-card?

That is what spycraft calls a "Dead Drop". During a "Dead Drop" the two operatives exchanging information
don't need to meet, which enhances operational security. Even if third parties are actively monitoring one
or even both operatives, the two will never be at the same place at the same time, therefore no useful information
can be gained by watching them. If they are careful enough, that is.

"Dead Drops" are real life things, although often using more sophisticated methods, like retrieving things from
places that are less visible than a park bench, like from inside a hotel room or digitally transferring information by radio
to some unseen device hidden in a wall, tree or rock.

This method of untraceable communication has now gone digital with 
<a href='http://play.google.com/store/apps/details?id=com.crowdymous.deaddrop'>
Crowdymous' Dead Drop App
</a>.

## Could a Dead Drop even work on the Internet?

If you're a somewhat internet savvy person, you might be thinking there's no way a Dead Drop would work online. On
the internet individual data packets are sent from one device to another, with both addresses present in these data
packets in the clear, letting everyone who is willing to listen know who is communicating with whom. This is
the case even if packets take the "scenic" route over multiple routers, devices, networks, etc. In essence
two devices *must meet* on the internet to communicate. This is at best a *Live* Drop, not a Dead Drop.

Indeed <a href="https://www.theverge.com/2015/11/11/9719098/fbi-reportedly-paid-1-million-carnegie-mellon-tor">it turns out</a>
that even on networks like <a href="https://www.torproject.org/">Tor</a>, which try to *obfuscate* who is talking
to whom by introducing multiple indirections and statistical noise,
long term and large scale monitoring of the network can lead to uncovering of the social nets of individuals. This
is not because of a bug, mind you, but because of how it is designed. By letting devices communicate interactively
a whole treasure-trove of statistical information is unleashed onto the internet for everyone to see. One can try
to mask it, obfuscate it, introduce noise, which makes analysis more difficult, but it can not be made
perfectly untraceable this way.

So, how do you send a message to someone over the internet and still stay untraceable?

## Threat Model on the Internet

A Threat Model is a list of capabilities you assign to your adversaries and a list of
countermeasures you deploy against those capabilities. Can your adversary follow you
around all day? Can they bug your hotel room? Can they follow all your potential contacts? Do they
have access to credit card histories? Etc.

In the physical world monitoring even one person is expensive. It needs a whole team of people to do,
cooperation of other parties, like hotels, dispatch centers, not even mentioning lots of hardware
like vehicles, gadgets, etc.

Monitoring on the internet, as most of us are probably aware already, is much-much cheaper. It is not
just cheaper, but can be done and *is* done on a large scale. Even worse, you can monitor someone
*retroactively*, looking back at what they were up to several days or even weeks before, using
stored data.

What capabilities can we realistically assign to our potential adversaries then? Let's take a look in detail.

### Let's assume all data on the internet is seen *and* collected.

Even if some piece of data is on the internet for a fraction of a second, we should assume
that it is captured and stored. This assumption may seem trivial, but has a lot of consequences.

While encrypting the data between peers protects somewhat (see later points) against seeing the *contents* of the data, 
what about the connections themselves? The existence of the connection between two devices can already
help to trace the people on both sides of the communication. Also, if one of them is already known, like a known journalist,
a specialist doctor, or a political group, the person communicating already potentially incriminates
herself or himself through affiliation alone.

You may have seen some VPN providers advertising that they "delete logs", or don't keep logs at all.
This has several problems (see next points), but the problem under this assumption is, that
the connection information *was* already out on the internet. It is not a secret. Sure, packets are
going from you to the VPN provider, and from the VPN provider to your destination, and the two
are not directly linked, but it *can* be linked by statistical information easily for someone
who has access to connection information on both sides.

For example an attacker seeing your traffic to be 10KB up / 100KB down just has to look
which connection from the VPN provider matches this traffic profile to connect you to your
destination. If a single instant is not enough, changes of this profile over time makes
this attack even easier.

This is not to say that VPNs are useless. VPNs operate under a different threat model for a different use-case,
which they do well, but for our purposes it is not enough.

For an untraceable communication there can not be *any* statistical data that leaks to the internet.
In other words, the physical act of sending and receiving data needs to be completely independent
from user action. If it is not, *some* information will eventually leak and compromise the user.

So how can the physical act of sending and receiving data be independent of user action? Quite
easily actually. Let's just make all devices send and receive at predefined intervals, regardless
of whether there are messages to be sent or received. To avoid traffic profiles, let's also
make all messages the same size. Although this introduces overhead, it solves all of the problems above.

### Let's assume companies can be forced to divulge encryption keys

Laws are different for different jurisdictions of course, but with all <a href="https://en.wikipedia.org/wiki/Global_surveillance_disclosures_(2013%E2%80%93present)">we know</a>
this is not even an assumption, more a fact for most. Even in jurisdictions where this is not
the case, laws can easily change for the worse.

Keys can obviously not be in the hands of the companies providing the service. The answer
is end-to-end encryption. I.e. the users themselves have keys, the secret parts of which
are never disclosed. Ever. Not even to the provider of the communication service.

Most "encrypted" communication apps already use end-to-end encryption this way.

### Let's assume companies can be forced to divulge *any and all* information they have, even if just for a split second

All current communication apps require some form of *routing*. That is, moving the
incoming message, even if it is end-to-end encrypted, to its intended receiver. To do this
the service *needs to know*, at least for a fraction of a second, who is talking to whom.

Even if the service tries its best not to record any of this information, it is still *available*. The
company can conceivably be forced by law to collect, log and/or provide this data upon request.

Another way to force this information out of the server is to crack (break into) the server either
digitally or even physically. This is why some companies try really hard to physically secure their servers, or try
to dissociate the user from their devices as well as possible.

But even if there is no law and the servers are physically secured, what about just paying an
employee to reveal some data? What about a disgruntled employee taking and revealing some data? *Any*
information the server knows the provider and its employees could potentially know as well. It is therefore at risk.

The only way to avoid all these problems however is to *not route*. Without the routing, the server doesn't need
to know anything at all, it is just a technical component that sits somewhere. Even if all the data
that is available on it is stolen, leaked or collected, there is nothing there. Not even
for a millisecond. No connections between devices, no contents, no contact lists, nothing.

The server *must* be oblivious to what's happening on it. But, how do we send a message to somebody without actually telling the server who it is for?

## Private Information Retrieval

A quick and easy solution for the server would be to just deliver *every* message to *every* user. In essence
creating a *broadcast* protocol, in which everybody sees everything. Because the messages
are end-to-end encrypted, arrive at pre-determined regular intervals, and are the same size (see previous points),
the server would not know what's going on at all. Also because of the end-to-end encryption users would only be 
able to actually read the message which was written explicitly for them, so it would still be perfectly secure.

This protocol would work, but would be extremely difficult to scale. If we assume a handheld
device with somewhat limited connectivity, receiving *all* messages from all the users worldwide
would quickly run into problems.

Luckily there's a new-ish field of cryptography called
<a href="https://en.wikipedia.org/wiki/Private_information_retrieval">Private Information Retrieval</a>.
Surprisingly, it is possible to query the server for a message without the server
finding out which message was queried *and* in a way that uses significantly less
bandwidth than downloading all messages.

So *PIR* is a way to query the server for a message without the server finding out what message, if any, 
was returned. The server is therefore at no time in possession of any information that would reveal
the existence of a communication, let alone the identities of parties involved, because it is unable to
make the connection between sender and receiver.

There are some trade-offs involved in using *PIR* however. It is computationally expensive
relative to other services that route messages. A server that routes messages can directly
answer a query by accessing the required message (or inbox). Every single *PIR* query however has to
calculate a cryptographic function over *all* messages. This is the only way the server
can stay oblivious to what message is selected by the query.

This makes a *PIR* based server costly to operate and more difficult to scale. This is the price
for untraceable communication.

## Putting in all together

Let's look at what tools we identified to implement a *Dead Drop* digitally:

* Dissociate user action from network traffic to avoid leaking statistical information.
Send / receive at predefined intervals, using uniform message sizes.
* End-to-end encryption with secret keys only on the user's device. This prevents access
by third parties anywhere on the internet, including the service provider.
* Using *PIR* to retrieve a message, leaving the server oblivious to what is happening,
instead of letting the server route messages and with it revealing the parties involved.

These are in fact the exact technologies used by
<a href='http://play.google.com/store/apps/details?id=com.crowdymous.deaddrop'>
Crowdymous' Dead Drop App
</a>
to provide **untraceable** communication to its users. A digital *Dead Drop*, that is even
easier to use than real-life ones.

