# 2018 First Year CompSci Project
## Benjamin Chalmers

# Idea: bCryptoChat

bCryptoChat is going to be a direct P2P chatting application that will send messeges using TCP/IP over the internet directly to the person with whom you are communicating.

This instant messaging proticol will implement my own ground up cryptolibrary, as such it is very unlikely to be 'secure' in the modern sense though I will do my best.
My encryption proticol will be hevily inspired by OTR, or Off The Record, which can be read about [here](https://otr.cypherpunks.ca/Protocol-v3-4.1.1.html).
This should allow the users three features.
First is end to end encryption from any packet sniffers without access to the private keys.
The second the communicators can verify the identity of the person with whom they are comunicating with.
Fourth is that chat logs are trivially spoofable by either party.
That is, all comunication is plausably deniable and cannot be verifiably leaked by either party, it is as secure in this sence as an unrecorded conversation.

Again I must stress **THIS IS NOT SECURE!!!!!!** This is an academic project by a first year computer science student, please do not use this for anything mission critical.
