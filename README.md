# OCR-with-Python-and-API
Recognize the text from a picture using Python and orc.space API.
OCR (Optical character recognition) is the process by which the computer recognizes the text from an image.
ocr.space is an OCR engine that offers free API.
It means that is going to do pretty much all the work regarding text detection. We only need to send through their API an image with the text we want to scan, and it will return us the text scanned.
## How to use ocr.space API?
First of all, you need to get an API key by registering to their website.
Go on http://ocr.space/OCRAPI and then click on “Register for free API Key”.
Once you have the key, follow the steps below.

## 1) Import the libraries and load the image
Let’s import all the libraries that we need (Opencv, IO, numpy, requests, json).
IO and Json are by default already installed on python, you should install the other libraries, if you haven’t done it yet.
Then we load the image. 
We can cut the image to select only the area where there is the text, in case the image contains some background.
