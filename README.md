# J296 Final: A data story about migrant deaths at the U.S.-Mexico border

## PART ONE - The Story

### The fatal journey: migrant deaths continue to rise at the U.S.-Mexico border 
By Mengyuan Dong

For immigrants fleeing from their home countries into the U.S. or those being sent back to Central America, crossing the border has become more and more deadly over the years. 

According to the International Organization for Migration, at least 714 people died trying to migrate across the border in 2021, the highest number since the agency began recording such incidents in 2014.

<img src="/year.png" alt="" width="60%">
(https://datawrapper.dwcdn.net/ICuze/1/)<br><br>

The International Organization for Migration started recording people who die in the process of migration towards an international destination after 2014. It has found at least 3599 deaths on the route to cross the U.S.-Mexico border, including the elderly and unborn fetuses. 

Some migrants were found dead in Mexico and other Central American countries, unable to make the journey due to drowning, exposure to the harsh environment, violence or other mortal conditions. However, about 83 percent of those migrants lost their lives in the U.S. territories last year. 

Arizona had the highest number of incidents among the four border states. At least 226 migrants have died along the Arizona border in 2021, according to data collected by an Arizona advocacy group Humane Borders in partnership with the Pima County Medical Examiner’s Office. The latter identifies human remains found around Arizona’s border with Mexico, collecting and sending data to Humane Borders for running a searchable map. 

Although there hasn’t been a significant jump compared to previous years, a record of 226 deaths is still the highest since 1981. 

<img src="/map.png" alt="" width="80%">
(https://public.flourish.studio/visualisation/9792531/)<br><br>

Mike Kreyche, the mapping coordinator at Humane Borders, said the increase in deaths could be correlated with climate change, as the data shows heat exposure is the most common reason that could take migrants’ lives. 

“Political considerations and economic depressions also have a lot to do with it.,” Kreyche said.

For the past two years, the federal government has turned away migrants at the U.S.-Mexico border, including those seeking asylum, using a public emergency health order known as Title 42. The U.S. Border Patrol reported more than 1.6 million encounters with migrants along the U.S.-Mexico border in the 2021 fiscal year, more than quadruple the number of the prior fiscal year and the highest annual total on record.

<img src="/cause of death.png" alt="" width="70%">
(https://datawrapper.dwcdn.net/eIcxu/1/)<br><br>

Humane Borders has long recognized the significance of saving people from death by exposure and dehydration. Since 2000, it has maintained a system of water stations in the Sonoran Desert used by migrants. Arizona’s vast public lands in the desert make the conditions along the migration routes harsher. 

Most of the migrant deaths and probably most of the migration take place either on tribal lands or public lands, Kreyche said. 

“Only a few ranchers, hikers and birdwatchers would go there,” Kreyche said. 

According to Regrid, a provider of nationwide land parcel data, about 57 percent of land around the Arizona border is publicly owned, and the majority of the Arizona border has some existing fencing in place. “Arizona portion of the border is some of the most punishing and remote, consisting mostly of desert and low scrub punctuated by rocky outcrops,” said in its 2020 report. 

Arizona also has by far the fewest privately-owned parcels by acreage along the border - just 3.7%, as compared to the overall border-wide statistic of 36.4%. 

<img src="/arizona lands.png" alt="" width="80%">
(https://datawrapper.dwcdn.net/cFxWc/1/)<br><br>

The growing number of migrant deaths is already striking, but it only reflects a small fraction of the brutal reality at the border.

“The remains can disappear very quickly out in the desert. I don’t think anybody really has an idea [how big the actual number is],” Kreyche said. 

The U.S. Border Patrol set up the Missing Migrant Program in 2017 to help rescue migrants in distress and reduce migrant deaths along the southwest border. It has also undertaken efforts such as placing rescue beacons and 9-1-1 placards in remote areas.

However, Advocates and agencies like the Government Accountability Office (GAO) urge the U.S. border Patrol to do a better job tracking and disclosing data on migrant deaths. According to GAO’s recent report, Border Patrol agents significantly undercount immigrant deaths, with the number of people dying likely twice as high as previously reported.

Kreyche said he is in a group trying to make a database for the whole southwest region, but there have been pushbacks from other states. 

“Texas has a problem with fragmentation of responsibility and there’s no good records there; New Mexico has a good data system but has not made it a practice to identify migrants in any way.” Kreyche said. “There may be a possibility of doing some collaboration with California.”

The latest incident on the record in 2022 was a migrant originally from Caribbean, who died due to sickness and lack of access to adequate healthcare in Yuma Regional Medical Center in Arizona.




## PART TWO - Dataset Analysis
### Data source 1:
* International Organization for Migration(IOM) https://missingmigrants.iom.int/downloads


### First Steps:
1. **Cleaning the data**. I was looking at the IOM data first. There were 10275 rows in total. After inspection, the data was very normalized and didn't require much refining, and there were no duplicates found. So I could start the analyzing process in Google Sheets.
2. **Opening the data in Google Sheets**. I made a copy of the dataset, froze the first row and made it bold.

### Q1: How many migrant deaths occurred at the U.S.-Mexico border? At which regions did the incidents happen?
1. Applied filter to the [Migration route] column, and selected "US-Mexico border crossing" only. 
2. Made a new sheet and pasted all incidents at the U.S.-Mexico border. There were 2698 incidents in the dataset. 
3. Made a pivot table into a new sheet and named it "Year". Selected [Incident year] as rows, and [number of dead] as values, and [Region of incident] as columns. 
<img src="/screenshot_year.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: The number of cases have been increasing each year, and 2021 has seen 714 incidents, the highest on record. About 83% of those incidents happened in the U.S. territory

### Q2: Which U.S. states had the most migrant deaths? 
1. As the dataset only had coordinates, I had to use geocodio to convert coordinates into addresses. 
2. In column [Coordinates], the data format looked like this: POINT (-110.366453 31.650259). I used the "SPLIT" function to split this into latitude and longitude, which made it easier for geocoding. 
(**There were 44 incidents that didn't have location information**)
3. Copied and Pasted the results into a new sheet called "long&lat", there were 2654 results in total. 
4. Downloaded sheet "long&lat" as a csv file, and uploaded it onto Geocodio. 2,502 out of 2,653 locations were geocoded successfully.
5. Created a pivot table into a new sheet and named it "state". Selected [States] as rows, and [Main ID] and [Number of Dead] as values.
<img src="/screenshot_state.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: Arizona had most incidents, and Texas had the highest number of deaths. (There might be more than one death in some incidents)

### Q3: How many dead migrants were men? And how many were women?
1. Created a pivot table into a new sheet and named it "gender". Selected [Incident year] as rows, and [Number of females] and [Number of males] as values.
<img src="/screenshot_gender.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: There were more male deaths than females each year. 

### Q4: What were some major causes of death?
1. Created a pivot table into a new sheet and named it "cause". Selected [Cause of death] as rows, [Number of dead] as values, and [Region of Incident] as columns.
2. For values, chose "show as % of grant total"; for rows, chose "sort by number of dead" in descending order.
<img src="/screenshot_cause.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: For incidents happened in Central America, the primary reason for death was "drowning"; while for those happened in North America, the primary reason was "harsh environmental conditions".<br><br>


### Data source 2:
* Humane Borders & Pima County Medical Examiner’s Office https://humaneborders.info/app/map.asp

### First Steps:
1. **Cleaning the data** This dataset was quite normalized as well. The only change I made was for the [causes of death] column, there were some blanks but also a category called "undetermined". I talked to the person who's responsible for maintaining the data, and he said the blanks were older cases that might be updated in the future. So I replaced all the blanks with "undeterminded". 
2. **Opening the data in Google Sheets**. I made a copy of the dataset, froze the first row and made it bold.

### Q5: What are the trends over time in the number of migrant deaths in Arizona, and is it also on the rise?
1. Since the original dataset didn't have a column for year, I used the "=YEAR" function to extract the year from the [reporting data] column.
2. Created a pivot table into a new sheet and named it "year". Selected [Year] as rows, [ML Number] as values.
<img src="/screenshot_year2.png" alt="The number of missing children was the highest in the 1990s" width="200px">

#### Findings: The number of incidents happened in 2021 was the highest on the record, but there was not a significant jump. 

### Q6: What were some major causes of migrant death in Arizona?
1. Created a pivot table into a new sheet and named it "reason". Selected [Cause of death] as rows, [ML Number] as values. Sorted the results in descending order.
<img src="/screenshot_cause2.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: "Exposure" was the biggest cause of migrant death in Arizona. 

### Q7: What was the maximum age, minimum age and average age of dead migrants in Arizona?
1. Using "=MAX", "=MIN" and "=AVERAGE" functions to calculate numbers in the [Age] column.
<img src="/screenshot_age.png" alt="The number of missing children was the highest in the 1990s" width="60%">

#### Findings: The maximun age of dead migrants was 99; the minimum age was 0, and that referred to three incidents of nonviable fetus (so heartbreaking). The average age was around 31.  

### Sources

* **Mike Kreyche**, mapping coordinator at Humane Borders (talked to)
* **Katy Murdza**, advocacy manager at Immigration Justice Campaign (reached out)
* **Eddie**(ECSouthTexasHumanRights@gmail.com), The South Texas Human Rights Center (reached out)

