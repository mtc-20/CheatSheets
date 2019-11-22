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
cv2.destroyAllWindows()
```

## Writing to file

`cv2.imwrite("Output", frame)` can be used to save a file
