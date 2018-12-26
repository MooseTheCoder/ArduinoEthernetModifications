# What is this place for?

I have been playing about with an arduino ethernet shield, powered by a w5100, I was having a problem with some data being cut off. 

After some digging around in the code, I managed to change the number of max connections and therefore allow me to increase the max buffer size.

This repo are the modifications I made, useless to anybody apart from me of course :D 

For anyone that stumbles upon this place and is wanting to change the buffer size, here is what I found. 

---- 

Enabling ````ETHERNET_LARGE_BUFFERS```` does not seem to fix the problem, in order to allow changes and basically have an unlimited buffer, you will also need to define the ````MAX_SOCK_NUM```` and bypass whatever is done with ````RAMEND```` and ````RAMSTART````.

This is most likley the wrong way to do things, but it worked for me. See line 37 to 55 in Ethernet.h to see what I did.
