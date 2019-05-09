# MSD internship
 ### If the notebook is not rendered in Github click on this link to view notebook [nb viewer link](https://nbviewer.jupyter.org/github/zszazi/MSD/blob/master/MSD_intern_final.ipynb)
 
 ### Google colab [notebook link](https://colab.research.google.com/github/zszazi/MSD/blob/master/MSD_intern_final.ipynb)
 
* I had some problem with accessing files in google colab even after wget the images from URL , so I downloaded a few images to my local machine and uploaded them to colab and ran the test*

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
 
%%time command was used to measure how long it took to run the algo

min_val,max_val,min_loc,max_loc was used to get coordinates of match and print a rectangle around it

**IMAGE**

![image](https://user-images.githubusercontent.com/41579863/57481850-b657b780-72c0-11e9-91eb-815dbc44a5eb.png)


**CROP**

![image](https://user-images.githubusercontent.com/41579863/57481899-d5564980-72c0-11e9-9217-38f0bb2d528e.png)

## 1. TM_CCOEFF
![image](https://user-images.githubusercontent.com/41579863/57481986-12bad700-72c1-11e9-88b1-88bacab58754.png)

*Coordinates* (11, 1) (101, 199)

*Run Time* CPU times: user 3 µs, sys: 1e+03 ns, total: 4 µs
Wall time: 9.06 µs





