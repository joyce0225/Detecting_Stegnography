# Steganography 📷

This project explores the use of LSB (Least Significant Bit) Steganography. Check out the accompanying Python script for implementing LSB steganography.

## Usage Instructions 🛠️

To embed a secret message:

`./stego -f <filename.png> -e <secret_message> -p <Password (Optional)>`

To extract the secret message:

`./stego -f <secretfile.png> -x -p <Password supplied>`

**Note**: Even if you pass a blank field in the `-p` argument while creating a secret file, you must append `-p` while extracting the message.

## What is Steganography? 🕵️‍♂️

Steganography comes from the Greek words *steganos* (meaning "covered") and *graphie* (meaning "writing"). It involves hiding a message within an image, audio, or video file. The technique utilizes the least significant bit to conceal the secret message, making the change undetectable to the naked eye.

### Types of Steganography:

- Image Steganography
- Audio Steganography
- Video Steganography
- Text files Steganography

### Types of Images:

- Black and White
- Grayscale
- RGB

In grayscale images, each pixel is represented in 8 bits. The last bit in a pixel, the least significant bit, affects the pixel value only by "1". This property is exploited to hide data within the image.

### LSB Steganography in Practice:

Consider a grayscale image where each pixel is represented by 8 bits (for RGB, it's 24 bits). For example, to hide the letter "A" (ASCII value: 10000001) in the following bits of a grayscale image:
   
    
    11110011
    11011010
    10110110
    11011100
    11011110
    11010110
    00100110
    01000011

The algorithm replaces the last bit of each byte with the consecutive bits of "A", resulting in:

    11110011
    11011010
    10110110
    11011100
    11011110
    11010110
    00100110
    01000011


## Steganalysis 🔍

Steganalysis involves detecting messages hidden using steganography. LSB Steganography can be detected by examining the histograms of files. Also, lossy compression techniques can render LSB Steganography ineffective, so lossless compression techniques are preferable.




