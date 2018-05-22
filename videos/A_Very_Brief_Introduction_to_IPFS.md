---
title: "A Very Brief Introduction to IPFS"
tags: ["IPFS"]
categories: ["Video", "Tutorial"]
date: "2017-09-07"
author: "Jason Rigden"
author_link: "https://jasonrigden.com/about/"
youtube: "F6OLeszJLB8"
---

### What is the InterPlanetary File System or IPFS?

**IPFS**  is a hypermedia protocol similar to  **HTTP**. In fact, IPFS intends to someday replace HTTP. Both are protocols for transferring files from a server to a client over the internet. These protocols can transfer any type of file from text to video. When you browse the web you are using HTTP to download  **HTML**  files from servers all over the world.

The advantage of using IPFS is data  **immutability**  and  **speed**.

### Data Immutability

Files on IPFS are given a generated hash value. A hash is kind of like a fingerprint for a file. Here is an example of a IPFS hash value:

_QmRW3V9znzFW9M5FYbitSEvd5dQrPWGvPvgQD6LM22Tv8D_

It is very long and unique. It would be almost impossible for two file to have the same hash. Hash values are the same for the same file. And hash values will change if the file is changes. These hash values act as an address. Using this address we can access the file. This is how the system achieves immutability. Nobody can change the file without the address changing. This also gives us deduplication of data. If both you and I upload the exactly same the javascript library to IPFS, we will both get the same hash address. So, this is immutability. Files added to IPFS can not be changed. When someone shares an IPFS address with me, I can be confident that the file I download has not been modified. Nobody can add malicious code to my javascript library.

### Data Speed & Resilience

Traditionally, HTTP has followed to simple client server model. A computer (the client) in Seattle request a file from a computer (the server) in New York City.

This can be slow or unreliable for many reasons. For example:

-   New York is far away from Seattle. It just takes longer to communicate due to distance even at the speed of light.
-   There could be lots and lots of clients asking the computer in New York for files.
-   The computer in New York can only serve so many clients.
-   Or maybe the computer in New York is not simply not turned on.

IPFS is a peer-to-peer protocol somewhat similar to Bittorrent. When I download a file some of that data can be shared with others. So maybe someone else in Seattle also downloaded that file from the server in New York. I could just download it from them. If a file is very popular then many people will have copies to share. This takes the load off the New York server and distributes it. Even if the server is turned off, I might still access the file. And I would be confident that nobody tampered with the file because of the immutability feature.

### Working with IPFS

#### Installing IPFS

Go to  [ipfs.io](https://ipfs.io/)  and download the software for your platform of choice. Follow the instruction for installation. The official docs are great but I will very quickly summarize them below.

#### Initialize

IPFS needs to initialized before we can use it.

ipfs init

#### Start the Daemon

The IPFS daemon must be running for us to use the system. Run this command in a separate terminal.

ipfs daemon

#### Adding a File

![](https://cdn-images-1.medium.com/max/800/1*JsNeqZxEj48JxQZfhtElSw.png)

This is my cat. Her name is Miss Hiss. She is a bit of a stinker.

We are going to add this cat picture to IPFS. The file name is  `cat_in_bag.png`Adding the file is quite simple.

ipfs add cat_in_bag.png

IPFS will output the the hash.

added QmR1VhhtXVvzw5zc12wj1CtohKh6DU7Y1MHpqRdhmrTZ7Y cat_in_bag.png`

#### Getting a File

Getting a file is pretty simple too. With this command the file you download will have the name  `QmR1VhhtXVvzw5zc12wj1CtohKh6DU7Y1MHpqRdhmrTZ7Y`  but it is still our cute cat pic.

ipfs get QmR1VhhtXVvzw5zc12wj1CtohKh6DU7Y1MHpqRdhmrTZ7Y

#### Conclusion

As stated in the title, this is just a very brief introduction to IPFS. There is much more to learn. For further reading I would recommend:

-   [The Official IPFS Documentation](https://ipfs.io/docs/)
-   [The Decentralized Web Primer](https://www.gitbook.com/book/flyingzumwalt/decentralized-web-primer/details)
