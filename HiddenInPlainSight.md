# Hidden In Plain Sight
## Steganography & Digital Watermarking

Presenter: Ryan Fox
Date: 04/13/2018

Ryan gave a very good talk about Steganography. He knew the subject domain
very well.

https://foxrow.com/assets/stego.pdf

Steganography is not Cryptography. Information is stored in a side channel, or
metadata channel. Can be in timestamp or image dimensions or encoded in the
pixels of an image.

Usually changing the least significant bit (LSB). Changes to the bottom two bits in
a pixel are difficult to detect. Ascii needs 8 bits per letter. Generally 1/2
bit per pixel is used.

### Detection and Attacks

It is difficult to prove a negative (the image has been modified).
Histogram (graph) of the four least significant bits can be used for detection.
In a normal image the LSB of pixels occur at the same rate, but in a
steganographic image that uses 1/2 bit per pixel the 0 and 1 bits are much
more statistically observed.

Hugo is AI to detect steganography.
Can use differential steganalysis to compare two images.

### Defeating Steganography
* Convert the image to grayscale
* Crop the image
* Redact portions of the image
* Skew or otherwise introduce noise

Steganography is used in the real world

* Digimark is a privately held company that does this.
* World of Warcraft screenshots contained info about a player account ID, server,
timestamp, etc.
* Font code uses slightly different characters to create a hidden message
* Anti counterfeiting currency (20 dollar bill, and Euros)
* Micro dots - Desktop printers print yellow dots to identify printer, time etc.
