# 2018 First Year CompSci Project
## Benjamin Chalmers

# Idea: bCryptoChat

bCryptoChat is going to be a direct P2P chatting application that will send messages using TCP/IP over the internet directly to the person with whom you are communicating.


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


