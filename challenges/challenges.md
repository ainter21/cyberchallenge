# Challenges

5. `hexdump -C staccah.jpg | less `, see [this](https://trailofbits.github.io/ctf/forensics/)
6. LSB half. Least significant bit. 
   1. 5.1 Least significant bit algorithm Least significant bit (LSB) insertion is a common, simple approach to embedding information in a cover image [12]. The least significant bit in other words, the 8th bit of some or all of the bytes inside an image is changed to a bit of the secret message. When using a 24-bit image, a bit of each of the red, green and blue colour components can be used, since they are each represented by a byte. In other words, one can store 3 bits in each pixel. An 800 × 600 pixel image, can thus store a total amount of 1,440,000 bits or 180,000 bytes of embedded data [16]. For example a grid for 3 pixels of a 24-bit image can be as follows: (00101101 00011100 11011100) (10100110 11000100 00001100) (11010010 10101101 01100011) 
   2. [website](https://georgeom.net/StegOnline/image)
7. Search for cookies
8. search for `robot.txt` file


## week 2

1. the password is `this-password-is-a-secret-to-everyone!`
2. use gdb to debug. Call the function printFlag() using this syntax: `print (char*) printFlag()`