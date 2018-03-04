---
title: bCryptoChat
author: Benjamin Chalmers (sc17b3c)
date: \today
documentclass: IEEEtran
...
\pagenumbering{gobble}

\begin{abstract}
The plan for the bCryptoChat project to be coded in C for COMP1921
\end{abstract}

# Summary

\IEEEPARstart{b}{CryptoChat} is going to be a direct P2P chatting application that will send messages using TCP/IP over the internet directly to the person with whom you are communicating.

This instant messaging protocol will implement my own ground up cryptolibrary, as such it is very unlikely to be 'secure' in the modern sense though I will do my best.
My encryption protocol will be heavily inspired by OTR, or Off The Record, which can be read about [here](https://otr.cypherpunks.ca/Protocol-v3-4.1.1.html).
This should allow the users three features.
First is end to end encryption from any packet sniffers without access to the private keys.
The second the communicators can verify the identity of the person with whom they are communicating with.
Fourth is that chat logs are trivially spoofable by either party.
That is, all communication is plausibly deniable and cannot be verifiable leaked by either party, it is as secure in this sense as an unrecorded conversation.

The 'Project' I will be shoe horning this into will be Project 4.
That is, 'The SDL library'. Which I will use as a way to draw pretty pictures or something to make the user feel a little happier whilst using the application.
The UI will be using GTK (3.0) or nCurses.

I'll be trying to use as few libraries as reasonably possible on this project, but as UI doesn't at all interest me I'll let GTK do the work here. I may even use nCurses, a library for displaying ourput to the terminal.
It would also be a thought to use a pre existing chat application such as pidgin or weechat to handle the user interface and allow the user to seamlessly integrate my new protocol with pre-existing solutions such as IRC or XMPP.
I'll also use some low level networking libraries (socket.h and types.h etc.
However all of the crypto stuff will be implemented entirely by myself and make up by far the bulk of the workload.

# Large-scale

This project, and it's implementation, should provide a highly secure platform for two peers to communicate.
It gives the ability to be secure against everyone, including the person with whom you are communicating.

# Medium-scale

I'll do this part in bullet points. I need to implement:

- A socket which listens for incoming communications.
- A socket which sends communications.
- An integer bignum library for the crypto
- A crypto library for the message decryption.
- Devise and implement a protocol for the instant messaging.
- Make the application usable.
- Use SDL to make a pretty picture, perhaps it could be a render image relating to the fingerprint of the person with whom you are talking. Thus allowing a comparison for additional security from man in the middle attacks.
- Potentially twitter/oe integration for the initial key and IP exchange.

The first stage will to be to write a clear text communication app, then I will go on to write the crypto.

# Testing

Because I'm a bit backward, I'll use GNU autotools/autotest for the make process. `./configure && make && make install` GNU goodness.
I'll write good tests for each element of my code before/as I am coding it.
I'll use Travis CI for running GitHub web hooked automated tests on my code each time I push it to my repository.

# Schedule

## Week 1

Some initial boiler plate project setup, and some initial coding on the TCP/ip aspect of comunicating.

## Week 2

Hopefully I can do a basic netcat style TCP/ip session of communication, work starts on UI.

## Week 3

Crypto time, now that we have a finished P2P messaging application.
Big num first

## Week 4

Big num should probably be done in its basic form, ASM optemisations will be continuously resarched and added.

## Week 5

Crypto time, decide on a really well defined proticol for my crypto communications.

## Week 6

Implement the crypto stuff, adding to the bignum aspect when and where needed.

## Week 7

Finishing touches, maybe add twitter intergration to do a public exchange of keys and IP (encrypted with keys) in order to establish an identity with out much risk of a P2P attack and wihout a DHT exposing your IP address to the unwashed masses.

## Week 8

Polish, add SDL for showing somthing fancy
