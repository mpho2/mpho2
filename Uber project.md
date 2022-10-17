
import numpy as np
import pandas as pd 
import matplotlib.pyplot as plt

import numpy as np
import pandas as pd 
import matplotlib.pyplot as plt
​
uber_df=pd.read_csv("uber.csv")
uber_df.tail(10)
START_DATE*	END_DATE*	CATEGORY*	START*	STOP*	MILES*	PURPOSE*
1146	12/30/2016 11:31	12/30/2016 11:56	Business	Kar?chi	Kar?chi	2.9	Errand/Supplies
1147	12/30/2016 15:41	12/30/2016 16:03	Business	Kar?chi	Kar?chi	4.6	Errand/Supplies
1148	12/30/2016 16:45	12/30/2016 17:08	Business	Kar?chi	Kar?chi	4.6	Meeting
1149	12/30/2016 23:06	12/30/2016 23:10	Business	Kar?chi	Kar?chi	0.8	Customer Visit
1150	12/31/2016 1:07	12/31/2016 1:14	Business	Kar?chi	Kar?chi	0.7	Meeting
1151	12/31/2016 13:24	12/31/2016 13:42	Business	Kar?chi	Unknown Location	3.9	Temporary Site
1152	12/31/2016 15:03	12/31/2016 15:38	Business	Unknown Location	Unknown Location	16.2	Meeting
1153	12/31/2016 21:32	12/31/2016 21:50	Business	Katunayake	Gampaha	6.4	Temporary Site
1154	12/31/2016 22:08	12/31/2016 23:51	Business	Gampaha	Ilukwatta	48.2	Temporary Site
1155	Totals	NaN	NaN	NaN	NaN	12204.7	NaN
​
uber_df.head(10)
uber_df.head(10)
START_DATE*	END_DATE*	CATEGORY*	START*	STOP*	MILES*	PURPOSE*
0	1/1/2016 21:11	1/1/2016 21:17	Business	Fort Pierce	Fort Pierce	5.1	Meal/Entertain
1	1/2/2016 1:25	1/2/2016 1:37	Business	Fort Pierce	Fort Pierce	5.0	NaN
2	1/2/2016 20:25	1/2/2016 20:38	Business	Fort Pierce	Fort Pierce	4.8	Errand/Supplies
3	1/5/2016 17:31	1/5/2016 17:45	Business	Fort Pierce	Fort Pierce	4.7	Meeting
4	1/6/2016 14:42	1/6/2016 15:49	Business	Fort Pierce	West Palm Beach	63.7	Customer Visit
5	1/6/2016 17:15	1/6/2016 17:19	Business	West Palm Beach	West Palm Beach	4.3	Meal/Entertain
6	1/6/2016 17:30	1/6/2016 17:35	Business	West Palm Beach	Palm Beach	7.1	Meeting
7	1/7/2016 13:27	1/7/2016 13:33	Business	Cary	Cary	0.8	Meeting
8	1/10/2016 8:05	1/10/2016 8:25	Business	Cary	Morrisville	8.3	Meeting
9	1/10/2016 12:17	1/10/2016 12:44	Business	Jamaica	New York	16.5	Customer Visit
​
uber_df.shape
(1156, 7)
uber_df.size
uber_df.size
8092
uber_df.info
 uber_df.info
<bound method DataFrame.info of            START_DATE*         END_DATE* CATEGORY*            START*  \
0       1/1/2016 21:11    1/1/2016 21:17  Business       Fort Pierce   
1        1/2/2016 1:25     1/2/2016 1:37  Business       Fort Pierce   
2       1/2/2016 20:25    1/2/2016 20:38  Business       Fort Pierce   
3       1/5/2016 17:31    1/5/2016 17:45  Business       Fort Pierce   
4       1/6/2016 14:42    1/6/2016 15:49  Business       Fort Pierce   
...                ...               ...       ...               ...   
1151  12/31/2016 13:24  12/31/2016 13:42  Business           Kar?chi   
1152  12/31/2016 15:03  12/31/2016 15:38  Business  Unknown Location   
1153  12/31/2016 21:32  12/31/2016 21:50  Business        Katunayake   
1154  12/31/2016 22:08  12/31/2016 23:51  Business           Gampaha   
1155            Totals               NaN       NaN               NaN   

                 STOP*   MILES*         PURPOSE*  
0          Fort Pierce      5.1   Meal/Entertain  
1          Fort Pierce      5.0              NaN  
2          Fort Pierce      4.8  Errand/Supplies  
3          Fort Pierce      4.7          Meeting  
4      West Palm Beach     63.7   Customer Visit  
...                ...      ...              ...  
1151  Unknown Location      3.9   Temporary Site  
1152  Unknown Location     16.2          Meeting  
1153           Gampaha      6.4   Temporary Site  
1154         Ilukwatta     48.2   Temporary Site  
1155               NaN  12204.7              NaN  

[1156 rows x 7 columns]>
().values.any()
uber_df.isnull().values.any()
True
ll().values.sum()
uber_df.isnull().values.sum()
507
df.isnull().values.any()
df=uber_df.dropna()
df.isnull().values.any()
False
u
uber_df.describe()
MILES*
count	1156.000000
mean	21.115398
std	359.299007
min	0.500000
25%	2.900000
50%	6.000000
75%	10.400000
max	12204.700000
"START*"]
un_start_destination=uber_df["START*"].dropna()
unique_start=set(un_start_destination)
unique_start
{'Agnew',
 'Almond',
 'Apex',
 'Arabi',
 'Arlington',
 'Arlington Park at Amberly',
 'Asheville',
 'Austin',
 'Banner Elk',
 'Bellevue',
 'Berkeley',
 'Boone',
 'Briar Meadow',
 'Bryson City',
 'Burtrose',
 'CBD',
 'Capitol One',
 'Cary',
 'Central',
 'Chalmette',
 'Chapel Hill',
 'Chessington',
 'College Avenue',
 'Colombo',
 'Columbia Heights',
 'Congress Ave District',
 'Connecticut Avenue',
 'Convention Center District',
 'Cory',
 'Couples Glen',
 'Covington',
 'Coxville',
 'Daytona Beach',
 'Downtown',
 'Durham',
 'Eagan Park',
 'Eagle Rock',
 'East Austin',
 'East Elmhurst',
 'East Harlem',
 'Eastgate',
 'Edgehill Farms',
 'El Cerrito',
 'Elk Park',
 'Elmhurst',
 'Emeryville',
 'Fairmont',
 'Farmington Woods',
 'Fayetteville Street',
 'Financial District',
 'Flatiron District',
 'Florence',
 'Fort Pierce',
 'Fuquay-Varina',
 'Galveston',
 'Gampaha',
 'Georgian Acres',
 'Gulfton',
 'Hayesville',
 'Hazelwood',
 "Hell's Kitchen",
 'Heritage Pines',
 'Holly Springs',
 'Houston',
 'Hudson Square',
 'Huntington Woods',
 'Ingleside',
 'Islamabad',
 'Jackson Heights',
 'Jacksonville',
 'Jamaica',
 'Jamestown Court',
 'K Street',
 'Kalorama Triangle',
 'Kar?chi',
 'Karachi',
 'Katunayaka',
 'Katunayake',
 'Katy',
 'Kenner',
 'Kilarney Woods',
 'Kissimmee',
 'Krendle Woods',
 'Lahore',
 'Lake Reams',
 'Lake Wellingborough',
 'Lakeview',
 'Latta',
 'Lexington Park at Amberly',
 'Long Island City',
 'Lower Garden District',
 'Lower Manhattan',
 'Mandeville',
 'Marigny',
 'Mcvan',
 'Mebane',
 'Medical Centre',
 'Menlo Park',
 'Meredith',
 'Meredith Townes',
 'Metairie',
 'Midtown',
 'Midtown East',
 'Morrisville',
 'Mountain View',
 'NOMA',
 'New Orleans',
 'New York',
 'Newark',
 'Newland',
 'Noorpur Shahan',
 'North Austin',
 'North Berkeley Hills',
 'Northwoods',
 'Nugegoda',
 'Oakland',
 'Old City',
 'Orlando',
 'Palo Alto',
 'Parkway',
 'Parkwood',
 'Pontchartrain Beach',
 'Pontchartrain Shores',
 'Port Bolivar',
 'Preston',
 'R?walpindi',
 'Raleigh',
 'Rawalpindi',
 'Red River District',
 'Redmond',
 'Renaissance',
 'Ridgeland',
 'Rose Hill',
 'SOMISSPO',
 'San Francisco',
 'San Jose',
 'Sand Lake Commons',
 'Santa Clara',
 'Savon Height',
 'Seaport',
 'Seattle',
 'Sharpstown',
 'Sky Lake',
 'Soho',
 'South',
 'South Berkeley',
 'South Congress',
 'Southside',
 'St Thomas',
 'Stonewater',
 'Storyville',
 'Sugar Land',
 'Summerwinds',
 'Sunnyside',
 'Sunnyvale',
 'Tanglewood',
 'Tenderloin',
 'The Drag',
 'Topton',
 'Townes at Everett Crossing',
 'Tribeca',
 'University District',
 'Unknown Location',
 'Wake Co.',
 'Wake Forest',
 'Washington',
 'Washington Avenue',
 'Waverly Place',
 'Wayne Ridge',
 'West Berkeley',
 'West End',
 'West Palm Beach',
 'West University',
 'Weston',
 'Westpark Place',
 'Whitebridge',
 'Winston Salem'}
len(unique_start)
len(unique_start)
177
stop_destination=uber_df["STOP*"].dropna()
unique_stop=set(stop_destination)
len(unique_stop)
188
']
uber_df[uber_df["START*"]=='San Francisco']
START_DATE*	END_DATE*	CATEGORY*	START*	STOP*	MILES*	PURPOSE*
362	5/9/2016 14:39	5/9/2016 15:06	Business	San Francisco	Palo Alto	20.5	Between Offices
440	6/14/2016 16:09	6/14/2016 16:39	Business	San Francisco	Emeryville	11.6	Meeting
836	10/19/2016 14:02	10/19/2016 14:31	Business	San Francisco	Berkeley	10.8	NaN
917	11/7/2016 19:17	11/7/2016 19:57	Business	San Francisco	Berkeley	13.2	Between Offices
919	11/8/2016 12:16	11/8/2016 12:49	Business	San Francisco	Berkeley	11.3	Meeting
927	11/9/2016 18:40	11/9/2016 19:17	Business	San Francisco	Oakland	12.7	Customer Visit
933	11/10/2016 15:17	11/10/2016 15:22	Business	San Francisco	Oakland	9.9	Temporary Site
966	11/15/2016 20:44	11/15/2016 21:00	Business	San Francisco	Berkeley	11.8	Temporary Site
topping
stopping_point = uber_df["START*"].dropna()
df = pd.DataFrame(starting_point.value_counts())
df.sort_values(["START*"],ascending=False)
​
df = df.reset_index()
df = df.rename(columns={'index':'starting_destination', 'START*':'Count'})
df.loc[df['Count']==max(df['Count'])]
starting_destination	Count
0	Cary	201
