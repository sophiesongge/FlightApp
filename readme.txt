The tests are done in Jupyter (with Anacomda). Question2 and Question3 have used Pandas. 
To use this code, you need to create a folder called "data", and put your files (bookings.csv and searches.csv)
inside this folder.
The results can be found in the "output" folder.

1. The code for Question1 is CountLines.ipynb, in this code, I choose to use a buffer to read each block of input file,
and count the number of '\n' inside each buffer, and add them up.

2. The code for Question2 is TopArrivalAirport.ipynb. For this one, I used Pandas. I first read bookings file in an iterative
way. It reads 10000 lines in each iteration (because this file contains 10000011 lines totally, it will have 1000 iteration
, and I sort the top 10 inside each iteration, and in the end it will have totally 10000 lines for the final sort, which makes each time we sort only 10000 lines, to avoid data skew). And I only use column 'arr_port' and 'pax'. I group by 'arr_port' and sort by 'pax'inside each iteration, then I put the intermediate tops inside each iteration in an array tops[]. And I sort tops[] in the end to get the global tops.

3. The code for Question3 is MonthlyNumber.ipynb. For this one, I also used Pandas, and read searches file in an iterative way.
I only use the columns 'Destination' and 'Date'. Inside each generation, I only kept the lines of 'AGP', 'MAD' and 'BCN'. After the iterative read, I use the 'Date' as the index for the new created DataFrame. I define each month by indexes, and count the appreance of 'AGP', 'MAD' and 'BCN' separately, and save the result in 3 arrays AGP[], MAD[] and BCN[]. And use these 3 arrays to draw the curve. Finally, I think that a histogram is more logical than a curve, so I create a file called PlotHistogram.ipynb to plot the results as a histogram.
