# OpenCV CheatSheet

# Contents
1. [Helper Library](#convenience)
2. [Displaying output](#display)
3. [Saving Files](#writing-to-file)
4. [Haar Cascade](#haar-cascade)
   1. [Trained Classifiers](#classifiers)
   2. [Cascade Trainer GUI](#gui)
5. [Object Tracking](#object-tracking)
---
## Convenience
`imutils` is a helper library for OpenCV, that simplifies the use of certain OpenCV functions: 
- The `PiVideoStream` class enables streaming from the Pi camera with multithreading, thereby improving FPS and overall performance.
- The `resize` function of `imutils` ensures that the aspect ratio of the original image is always maintained when resizing.

The `pip` command can be used to install the library.

```
pip install imutils
```

Do check out the [imutils GitHub repo](https://github.com/jrosebr1/imutils) for more of the useful features. Maybe even check out his blog which has a ton of tutorials on OpenCV, ranging from simple image processing to motion detection to deep learning.

---
## Display
If you're somebody like me who prefers to or always runs scripts fromk within an IDE (eg. Spyder), then remember to always accompany `imshow` command with the `waitKey()` and `destroyAllWindows()` commands.

**Images**

It's less complicated when dealing with just images. The below code closes the window when any key is pressed
```
cv2.imshow("Ouput", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
Or just use this function, if the script requires displaying multiple images.
```
import cv2

def display(img):
    #here, img refers to the numpy array form of the image and not the actual image
    cv2.imshow("Output", img)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
    
```
**Video or Camera Feed**

This code should go immediately below the `imshow` command.
```
  k = cv2.waitKey(1)
  if k%256 == 27:
    print ("[INFO] Escape hit, closing...")
    break
    
# This should go outside the loop
cv2.destroyAllWindows()
```
The `27` in the above code is the hexadecimal escape sequence for the <kbd>Esc</kbd> key.

___
## Writing to file
### Saving Images

`cv2.imwrite("Output.png", frame)` can be used to save a file.

Use the below code to save images from a video stream to the current directory. 

**Very useful for creating datasets for machine learning.**
```
import cv2

cap = cv2.VideoCapture(0)
ctr = 1

while True:
    ret, frame = cap.read()
    cv2.imshow('Test',frame)
    k = cv2.waitKey(1)

    if k%256 == 27:
        # ESC pressed
        print("[INFO] Escape hit, closing...")
        break
        
    elif k%256 == 32:
        # SPACE pressed
        img_name = "Image_{}.png".format(ctr)
        cv2.imwrite(img_name, frame)
        print("[INFO] {} written!".format(img_name))
        ctr += 1
        
cap.release()
cv2.destroyAllWindows()
```
### Saving Video
```
import cv2

cap = cv2.VideoCapture(0)

# Define the codec and create VideoWriter object
out = cv2.VideoWriter('output.avi', -1, 20.0, (640,480))

while(cap.isOpened()):
    ret, frame = cap.read()
    if ret==True:
        frame = cv2.flip(frame,0)

        # write the flipped frame
        out.write(frame)

        cv2.imshow('frame',frame)
        k= cv2.waitKey(1)
        
        if k%256==27:
            print("[INFO] Escape hit, closing...")
            break
    else:
        print("[INFO] Unable to access video. Exiting...")
        break

# Release everything if job is finished
cap.release()
out.release()
cv2.destroyAllWindows()
```
Do a test run first, in case the file isn't saved properly, then the right resolution has to be passed when declaring `out`.

______
## HAAR CASCADE
An object detection algorithm proposed by Paul Viola and Michael Jones, is a machine learning algorithm that is effective and light for binary classification.

The newer versions of OpenCV, while supporting the use of the classifiers, no longer support training your own classifiers; unless maybe you build from source.

So, to train your own classfier using OpenCV, create a virtual environment and install an OpenCV version older than 3.4. Then, these are good starting points: 
- [Naotoshi Seo][sonots]
- [Dileep Kumar][opencvuser]

### Classifiers
The xml files of trained classifiers can be found inside the OpenCV installation directory as well. Alternatively, you could just download the ones you require from [their GitHub repo][opencvdata].

### GUI
Alternatively, if, like me, you don't like dealing with environments, then there is this amazing GUI package from [Amin Ahmadi][ctgui] which works on Windows 10!
____
## OBJECT TRACKING
OpenCV has modules that allow tracking of objects. The computer vision models require that the object to be tracked be present in the first frame and it's bounding box be defined.
The scripts and more details have been compiled in [this repo][objtrk]




[sonots]:http://note.sonots.com/SciSoftware/haartraining.html
[opencvuser]:http://opencvuser.blogspot.com/2011/08/creating-haar-cascade-classifier-aka.html
[ctgui]:https://amin-ahmadi.com/cascade-trainer-gui/
[opencvdata]:https://github.com/opencv/opencv/tree/master/data/haarcascades
[objtrk]:https://github.com/mtc-20/Object_Tracking
