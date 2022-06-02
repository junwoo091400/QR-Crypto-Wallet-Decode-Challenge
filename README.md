# QR Code Crypto Wallet Decode Project

## Background
![QR Shirt Image](./QR_shirt_images/QR_Crypto_Slack_original.jpg)
There was this guy at the Student Project House (Makerspace) group that challenged everyone to scan his T-shirt and get the $30 out of his crypto wallet. And, I wanted it.

The problem was:
1. I was not physically at the Makerspace, so I couldn't go up to him and scan the QR code
2. The QR code in the picture posted on Slack showed only ~60% of the QR code

But I knew:
1. QR codes are error-resistant: Even if you remove upto 30% of the QR code's content (those little dots), the Reed-Solomon algorithm automatically corrects it to figure out the original content!
2. I wanted that crypto wallet content!

## Goal
1. Decode and get the $30 out of the challenger's wallet via extracting the info from the QR code
2. Create a program that can figure out the correct missing bits of the QR code, if certain parts are occluded!

## Plan
1. Manually copy the dots (bits) of the QR code from the [images](./QR_shirt_images/) and try to scan it bare-bone
   - If that doesn't work, figure out what the QR code means manually by going through the QR code spec (figure out the Error correction level, Mask type, etc.)
2. If that doesn't work, create a program that will fill in the occluded bits and figure out the original QR code content
   - Figure out which QR code spec the T-shirt belongs to
   - Search for existing QR code libraries that supports reading in any QR code formats (string, binary, etc)
   - Create a class that can hold the QR code information
   - Utilize the QR code error correction algorithm to correctly try out different combinations of occluded bits, and verify if the content makes sense

## Information on the QR code itself
- The Crypto Wallet QR code is 33 x 33 (modules), which is Version 4 of the QR code specification, which can hold from 34 to 78 bytes of data depending on error correction level (https://www.qrcode.com/en/about/version.html)
- 