# Searching-Eclipsing-Binaries-with-TESS
Using the TESS 30-min interval full frame images, this code searches for eclipsing binaries with convolutional neural network (CNN). 

<!--  -->
![[FSR2007] 0728 [15,12]](https://user-images.githubusercontent.com/49893001/91675214-6b366900-eaf0-11ea-95d2-8bb495d4a47f.png)

## Getting Started

This python script can be used to search for EBs in a cluster or any region of the sky covered by TESS. It returns a graph and .dat document for each pixel, which include information about the CNN prediction on the light curve of the pixel. 

### Prerequisites

Packages needed to run this script include
```
pickle, tensorflow, sklearn, astroquery
```

### Installing
After installing required packages, clone the master folder and run Searching_EB-Command_line.py on a command line. Locate tess_cnn.h5 file in CNN Training folder and you can start using it!

## Running the Search
The script askes for several parameters and saves figures and data that are selected by these parameters. The time taken for each pixel is roughly 6 seconds. Below is an example for the open cluster [FSR2007] 0728, which returns the figure shown above. This is a 400 pixel cut, and it took approximately 40 minutes in a test run. 

```
Target Identifier: [FSR2007] 0728
FOV in arcmin (max 33) [Default: 5]: 6.7
Trained cnn .h5 file [Default: tess_cnn.h5]:
#################################
  sectorName   sector camera ccd
-------------- ------ ------ ---
tess-s0019-1-3     19      1   3
#################################
Please choose a threshold to save a figure. This number is the prediction given by cnn, 
indicating the likelihood of including eclipsing binaries in a light curve. 0 is the 
lowest (keeping every pixel), and 1 is the highest (maybe excluding everything).
Threshold [Default: 0.95]: 0.99
Saving figures to [Default: root]:
Finished pixels:  ███████████████████∙∙∙∙∙∙∙∙∙∙∙∙∙ 60.0% Elapsed: 1514s Remaining: 1003s
```
Change the target and size of the cut to test it on any target. Note: Each TESS pixel is about 21 arcsec wide.


## Contributers

* **Te Han** 
* **Timothy D Brandt** 

## License
 ...
