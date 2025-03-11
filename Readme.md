# Scenario
Our cat, Gado, has been kidnapped. The kidnapper has sent us a document with their requests in MS Word Document format. We have converted the document to PDF format and extracted the image from the MS Word file for your convenience.

You can download the attached file below to your local machine for inspection. 

## Process
As we have a doc file from the kidnapper. We can get usefull information by analyzing that doc file.
To analyze it write 
```
pdfinfo
```
**Pdfinfo** displays various metadata related to a PDF file, such as title, subject, author, creator, and creation date. 

If you don't have pdfinfo installed, you can install it using 
``` 
sudo apt install poppler-utils 
```
![pdfinfo](https://github.com/AbuHanifSiam/Digital-Forensics-TryHackMe-/blob/d75585c9c42daa9513975b60484bdd3405e43653/Digital%20Forensics%20Images/fig%201.png)


From the screenshot we can see, we get some details of the file. When it was created and which software was used to create it.
The PDF metadata clearly shows that it was created using MS Word for Office 2016 on February 23, 2022.


## Photo EXIF Data
EXIF stands for Exchangeable Image File Format; it is a standard for saving metadata to image files. Whenever you take a photo with your smartphone or with your digital camera, plenty of information gets embedded in the image. The following are examples of metadata that can be found in the original digital images:

    --> Camera model / Smartphone model
    --> Date and time of image capture
    --> Photo settings such as focal length, aperture, shutter speed, and ISO settings

Because smartphones are equipped with a GPS sensor, finding GPS coordinates embedded in the image is highly probable. The GPS coordinates, i.e., latitude and longitude, would generally show the place where the photo was taken.

you can install it using 
```
sudo apt install libimage-exiftool-perl
```

![exiftool](https://github.com/AbuHanifSiam/Digital-Forensics-TryHackMe-/blob/d75585c9c42daa9513975b60484bdd3405e43653/Digital%20Forensics%20Images/fig%202.1.png)


![exiftool](https://github.com/AbuHanifSiam/Digital-Forensics-TryHackMe-/blob/d75585c9c42daa9513975b60484bdd3405e43653/Digital%20Forensics%20Images/fig%202.2.png)

If you take the above coordinates and search one of the online maps, you will learn more about this location. Searching Microsoft Bing Maps or Google Maps for 51 deg 30' 51.90" N, 0 deg 5' 38.73" W reveals the street where the photo was taken. Note that for the search to work, we had to replace deg with ° and remove the extra white space. In other words, we typed 51°30'51.9"N 0°05'38.7"W in the map search bar.

![google map](https://github.com/AbuHanifSiam/Digital-Forensics-TryHackMe-/blob/6b68542b35576a6ac6f2be06bf28ca98f2d72700/Digital%20Forensics%20Images/fig%203.png)
