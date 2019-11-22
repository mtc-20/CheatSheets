# OpenCV CheatSheet

# Contents
1. [Helper Library](#convenience)
2. [Displaying output](#display)
3. [Saving Files](#writing-to-file)


## Convenience
`imutils` is a helper library for OpenCV, that simplifies the use of certain OpenCV functions: 
- The `PiVideoStream` class enables streaming from the Pi camera with multithreading, thereby improving FPS and overall performance.
- The `resize` function of `imutils` ensures that the aspect ratio of the original image is always maintained when resizing.

The `pip` command can be used to install the library.

```
pip install imutils
```

Do check out the [imutils GitHub repo](https://github.com/jrosebr1/imutils) for more of the useful features. Maybe even check out his blog which has a ton of tutorials on OpenCV, ranging from simple image processing to motion detection to deep learning.

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
