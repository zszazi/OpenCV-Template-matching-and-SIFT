

## I used the following Algorithms 
### 1. SIFT(Scale-invariant feature transform)
### 2. Template Matching 

## 1. SIFT(Scale-invariant feature transform) Feature Matching

### If the notebook is not rendered in Github click on this link to view notebook [SIFT feature Matching nb viewer link](https://nbviewer.jupyter.org/github/zszazi/MSD/blob/master/SIFT_feature_matching.ipynb)
 
 ### Google colab [notebook link](https://colab.research.google.com/github/zszazi/MSD/blob/master/SIFT_feature_matching.ipynb)

## 2. Template Matching 
 ### If the notebook is not rendered in Github click on this link to view notebook [Template Matching nb viewer link](https://nbviewer.jupyter.org/github/zszazi/MSD/blob/master/template_matching.ipynb)
 
 ### Google colab [notebook link](https://colab.research.google.com/github/zszazi/MSD/blob/master/template_matching.ipynb)
 
I had some problem with accessing files in google colab even after wget the images from URL , so I downloaded a few images to my local machine and uploaded them to colab and ran the test

make sure to change the image file name to try with different images

# 1. SIFT Feature Matching
Can find the match even if image is rotated or differently oriented

**Image**

![image](https://user-images.githubusercontent.com/41579863/57636447-c4f6e500-75c6-11e9-8a5a-8b1732aaf01b.png)

**Crop**

![image](https://user-images.githubusercontent.com/41579863/57637141-4733d900-75c8-11e9-804e-4f8af21309bb.png)

**After Performing SIFT**

![image](https://user-images.githubusercontent.com/41579863/57637197-6468a780-75c8-11e9-918f-ed96f220a739.png)

![image](https://user-images.githubusercontent.com/41579863/57637229-819d7600-75c8-11e9-8375-50e49b7b2c21.png)

*Runtime* CPU times: user 2 µs, sys: 1 µs, total: 3 µs
Wall time: 6.2 µs

### Another Advantage of SIFT is that even if the template is rotated still it finds the match

 **Rotate Crop by 90 degrees**
 
 ![image](https://user-images.githubusercontent.com/41579863/57637320-c2958a80-75c8-11e9-95ae-3115d6f07d1a.png)
 
 **Result**
 
 ![image](https://user-images.githubusercontent.com/41579863/57637351-d6d98780-75c8-11e9-88c7-30585b84b439.png)
 
 We can clearly see that even though the image template has been rotated yet it captured the match in the image, although the back leg has not been matched
 
 The above undetected back leg can be solved by increasing the threshold although the noise make it indistinguishable
 
 **Results**
 
 ![image](https://user-images.githubusercontent.com/41579863/57637453-186a3280-75c9-11e9-855c-89ca686b331b.png)


# 2. Template Matching

**I approached the problem in the below ways**
1. If there is a template match
2. if there is no template match
3. If there is multiple template matches


**Open CV provides 6 inbuilt functon for template matching and I used all of them to compare the results**
1. TM_CCOEFF

2. TM_CCOEFF_NORMED

3. TM_CCORR

4. TM_CCORR_NORMED

5. TM_SQDIFF

6. TM_SQDIFF_NORMED
 
**%%time** command was used to measure how long it took to run the algo

min_val,max_val,min_loc,max_loc was used to get **coordinates of match** and print a rectangle around it

**IMAGE**

![image](https://user-images.githubusercontent.com/41579863/57481850-b657b780-72c0-11e9-91eb-815dbc44a5eb.png)


**CROP**

![image](https://user-images.githubusercontent.com/41579863/57481899-d5564980-72c0-11e9-9217-38f0bb2d528e.png)

## 1. TM_CCOEFF
![image](https://user-images.githubusercontent.com/41579863/57481986-12bad700-72c1-11e9-88b1-88bacab58754.png)

*Coordinates* (11, 1) (101, 199)

*Run Time* CPU times: user 3 µs, sys: 1e+03 ns, total: 4 µs
Wall time: 9.06 µs

## 2. TM_CCOEFF_NORMED
![image](https://user-images.githubusercontent.com/41579863/57482101-6a594280-72c1-11e9-8e4e-cb835823aeb7.png)

*Coordinates* (37, 12) (102, 199)

*Run time* CPU times: user 3 µs, sys: 1e+03 ns, total: 4 µs
 Wall time: 8.11 µs
 
 
 ## 3. TM_CCORR
 ![image](https://user-images.githubusercontent.com/41579863/57482207-a9879380-72c1-11e9-985c-4f12d5be8c83.png)
 
*Coordinates* (116, 190) (0, 81)

*Run time* CPU times: user 4 µs, sys: 1 µs, total: 5 µs
Wall time: 9.3 µs

## 4. TM_CCORR_NORMED
![image](https://user-images.githubusercontent.com/41579863/57482295-ed7a9880-72c1-11e9-981b-a446aa0f3072.png)
 
*Coordinates* (50, 193) (0, 425)

*Run time* CPU times: user 0 ns, sys: 8 µs, total: 8 µs
Wall time: 14.8 µs

## 5. TM_SQDIFF
![image](https://user-images.githubusercontent.com/41579863/57482407-2b77bc80-72c2-11e9-9751-05a47910ab58.png)

*Coordinates* (104, 199) (0, 54)

*Run time* CPU times: user 3 µs, sys: 1 µs, total: 4 µs
Wall time: 7.39 µs

## 6. TM_SQDIFF_NORMED

![image](https://user-images.githubusercontent.com/41579863/57482484-5e21b500-72c2-11e9-8990-2dcb874eb293.png)

*Coordinates* (103, 199) (0, 0)

*Run time* CPU times: user 5 µs, sys: 2 µs, total: 7 µs
Wall time: 7.39 µs

TM_CCORR AND TM_CCORR_NORMED were no where close to the match results

## Incase if the crop was not found

The best among the results where from TM_SQDIFF_NORMED

![image](https://user-images.githubusercontent.com/41579863/57482604-ae991280-72c2-11e9-8c7f-667c6e0c7b7f.png)

*Run time* CPU times: user 5 µs, sys: 2 µs, total: 7 µs
Wall time: 7.63 µs

## Incase of multiple crop matches 
**IMAGE**

![image](https://user-images.githubusercontent.com/41579863/57482671-e30cce80-72c2-11e9-957c-d9f119cb0c6d.png)

**Multi template crop**

![image](https://user-images.githubusercontent.com/41579863/57482703-f28c1780-72c2-11e9-8ed2-fafa3f30419c.png)

**Results**

![image](https://user-images.githubusercontent.com/41579863/57482752-10597c80-72c3-11e9-86a9-d91dbe3f0a7c.png)

*Run time* CPU times: user 2 µs, sys: 1e+03 ns, total: 3 µs
Wall time: 6.2 µs



### TO DO 
1. Multi Scale Template matching
2. Template matching in video


 
