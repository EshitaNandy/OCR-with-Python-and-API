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
## 2) Set the OCR engine
We now have the image and our goal is to send the image to the orc.space server in order to be processed.
On line 13 we have the url of ocr.space api where we need to send our image.
On line 14 we’re going to compress the image in JPG format. The simple reason for this compression is that using the free service we can send image with maximum 1mb of size, so this compression will shrink the size of our image.
On line 15 we convert the image into bytes. It must be converted to bytes to be sent to the server.
## 3) Later we send the bytes to the server using the python library requests.
We need to pass three parameters:
i. The first is the url_api
ii. Called “Files” which contains the name of the file and the file bytes we generated before after we compressed the image.
iii. And then “Data” which contains the post parameters of the OCR engine.
We need to insert the api key where now it’s written “YOURAPIKEYHERE”, and language is the language of our text. By default is english.
Go on this page http://ocr.space/OCRAPI to see all the “POST parameters” we can use.
The function is going to send the image to the server and in return we’re going to get the response from the server.
## 4) Read the Result
The result from the server is a string.
We’re going first of all to extract the content of result, then we convert the content into a dictionary.
Result contains the text read from the OCR engine plus a few other values. The other values depend from the post parameters we did set before.
For example if we enabled the text Overlay we would get the coordinates with the position of the text in the image.
Now from the result let’s extract only the text as it is our focus on this project:
