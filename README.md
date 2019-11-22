# HW4

## Problem 1

Given the decision I made in HW3, which is cut 15% budget for all districts, the proportion of each district’s total funding that will be lost is 15%. So the visualization will be all 15%.

![](https://github.com/stiangithub/HW4/blob/master/pr1.png)

According to my calculation, NYC CHANCELLOR'S OFFICE, Los Angeles Unified, City of Chicago SD 299, DADE	and HILLSBOROUGH will be the top 5 districts that are affected most.

## Problem 2

Since all districts' budget will be cut in my solution, so here I calculate & visualize for all districts.

```python
data = pd.read_csv("/Users/stian/Desktop/DS5500/hw4/ccd_lea_052_1516_w_1a_011717.csv")
data.columns.values
race_data = data[['LEAID', 'TOTAL', 'AM', 'AS', 
           'HI', 'BL', 'WH', 'HP', 'TR']]
race_data = race_data[race_data['TOTAL'] > 0]
race_data['AM_proportion'] = race_data['AM'] / race_data['TOTAL']
race_data['AS_proportion'] = race_data['AS'] / race_data['TOTAL']
race_data['HI_proportion'] = race_data['HI'] / race_data['TOTAL']
race_data['BL_proportion'] = race_data['BL'] / race_data['TOTAL']
race_data['WH_proportion'] = race_data['WH'] / race_data['TOTAL']
race_data['HP_proportion'] = race_data['HP'] / race_data['TOTAL']
race_data['TR_proportion'] = race_data['TR'] / race_data['TOTAL']
```

American Indian or Alaska Native:
![AM](https://github.com/stiangithub/HW4/blob/master/AM.png)

Asian
![AS](https://github.com/stiangithub/HW4/blob/master/AS.png)

Black or African American
![BL](https://github.com/stiangithub/HW4/blob/master/BL.png)

Hispanic/Latino
![HI](https://github.com/stiangithub/HW4/blob/master/HI.png)

White
![WH](https://github.com/stiangithub/HW4/blob/master/WH.png)

Hawaiian or Pacific Islander
![HP](https://github.com/stiangithub/HW4/blob/master/HP.png)

Two or More Races
![TR](https://github.com/stiangithub/HW4/blob/master/TR.png)

Again, according to my solution, the distributions are all same. There is no bias.

## Problem 3

``` Python
dis = pd.read_csv("/Users/stian/Desktop/DS5500/hw4/ccd_lea_002089_1516_w_1a_011717.csv")
dis = dis[['LEAID', 'SPECED']]
dis = dis.merge(race_data)
dis = dis[dis['SPECED']>=0]
dis['dis_proportion'] = dis['SPECED'] / dis['TOTAL']
```

As introduced before, according to my solution, all districts will receive cut. So here I visualize for all districts.

![pr3](https://github.com/stiangithub/HW4/blob/master/PR3.png)

The distribution is the same. There is no bias.



