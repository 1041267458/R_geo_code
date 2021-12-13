# R_geo_code


  This is a bunch of R codes created by Yinan Feng
  
  Including:
  - Calculate the pixel size
  - Insert the missing values of GRACE data
  
## Calculate the pixel size
  This is a R function to calculat the relatively accurate area of a raster data at degree resolution.
  The bsic idea and explaination are orignated from  whuber's answer in StackExchange <br/>
  [StackExchange:more accurate way to calculate area of rasters](https://gis.stackexchange.com/questions/127165/more-accurate-way-to-calculate-area-of-rasters) <br/>
  Calculate m^2 area of a wgs84 square pixel. <br/>
  May available in other CRSs by defining the right "a" and "b" <br/>
 
 Parameters: <br/>
 
  pixel_size (float): length of side of pixel in degrees. <br/>
  center_lat (float): latitude of the center of the pixel. Note this <br/>
  value +/- half the `pixel-size` must not exceed 90/-90 degrees <br/>
  latitude or an invalid area will be calculated. <br/>
 
 Returns: <br/>
 
  Area of square pixel of side length `pixel_size` centered at <br/>
  `center_lat` in m^2 <br/>
  "mosaic" package needed <br/>
  
  For users haven't download package "mosaic", <br/>
  please download the package by run following code in console : <br/>
  'install.packages("mosaic")' <br/>
  
## Insert the missing value of GRACE data
  
  This is a R code to insert the missing  value of GRACE data
  The GRACE gravity satellite data have many missing values due to the regular battery maintenance schedule.
  To reduce the bias caused by direct insertion of the average values, 
  I use monthly averages for interpolation.
  
  -Comparing the data's time sequence with complete time sequence <br/>
  -Calcaulate the monthly mean of GRACE data <br/>
  -According the missing date, interst the monthly acerage of the corresponding month <br/>
