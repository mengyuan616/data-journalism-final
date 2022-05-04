# J296 Final: A data story about migrant deaths at the U.S.-Mexico border
By Mengyuan Dong <br><br>

## Dataset 1
### Data source:
* International Organization for Migration(IOM) https://missingmigrants.iom.int/downloads


### First Steps:
1. **Cleaning the data**. I was looking at the IOM data first. There were 10275 rows in total. After inspection, the data was very normalized and didn't require much refining, and there were no duplicates found. So I could start the analyzing process in Google Sheets.
2. **Opening the data in Google Sheets**. I made a copy of the dataset, froze the first row and made it bold.

### Q1: How many migrant deaths occurred at the U.S.-Mexico border? At which regions did the incidents happen?
1. Applied filter to the [Migration route] column, and selected "US-Mexico border crossing" only. 
   (screenshot-region column)
2. Made a new sheet and pasted all incidents at the U.S.-Mexico border. There were 2698 incidents in the dataset. 
3. Made a pivot table into a new sheet and named it "Year". Selected [Incident year] as rows, and [number of dead] as values, and [Region of incident] as columns. 
   (screenshot-year)
#### Findings: The number of cases have been increasing each year, and 2021 has seen 714 incidents, the highest on record. About 83% of those incidents happened in the U.S. territory

### Q2: Which U.S. states had the most migrant deaths? 
1. As the dataset only had coordinates, I had to use geocodio to convert coordinates into addresses. 
2. In column [Coordinates], the data format looked like this: POINT (-110.366453 31.650259). I used the "SPLIT" function to split this into latitude and longitude, which made it easier for geocoding. 
(**There were 44 incidents that didn't have location information**)
3. Copied and Pasted the results into a new sheet called "long&lat", there were 2654 results in total. 
4. Downloaded sheet "long&lat" as a csv file, and uploaded it onto Geocodio. 2,502 out of 2,653 locations were geocoded successfully.
5. Created a pivot table into a new sheet and named it "state". Selected [States] as rows, and [Main ID] and [Number of Dead] as values.
   （screenshot_year）
#### Findings: Arizona had most incidents, and Texas had the highest number of deaths. (There might be more than one death in some incidents)

### Q3: How many dead migrants were men? And how many were women?
1. Created a pivot table into a new sheet and named it "gender". Selected [Incident year] as rows, and [Number of females] and [Number of males] as values.
   (screenshot_gender)
#### Findings: There were more male deaths than females each year. 

### Q4: What were some major causes of death?
1. Created a pivot table into a new sheet and named it "cause". Selected [Cause of death] as rows, [Number of dead] as values, and [Region of Incident] as columns.
2. For values, chose "show as % of grant total"; for rows, chose "sort by number of dead" in descending order.
   (screenshot_cause)
#### Findings: For incidents happened in Central America, the primary reason for death was "drowning"; while for those happened in North America, the primary reason was "harsh environmental conditions".<br><br>


## Dataset 2
* Humane Borders & Pima County Medical Examiner’s Office https://humaneborders.info/app/map.asp

### First Steps:
1. **Cleaning the data** This dataset was quite normalized as well. The only change I made was for the [causes of death] column, there were some blanks but also a category called "undetermined". I talked to the person who's responsible for maintaining the data, and he said the blanks were older cases that might be updated in the future. So I replaced all the blanks with "undeterminded". 
2. **Opening the data in Google Sheets**. I made a copy of the dataset, froze the first row and made it bold.

### Q5: What are the trends over time in the number of migrant deaths in Arizona, and is it also on the rise?
1. Since the original dataset didn't have a column for year, I used the "=YEAR" function to extract the year from the [reporting data] column.
2. Created a pivot table into a new sheet and named it "year". Selected [Year] as rows, [ML Number] as values.
   (screenshot_year2)
#### Findings: The number of incidents happened in 2021 was the highest on the record, but there was not a significant jump. 

### Q6: What were some major causes of migrant death in Arizona?
1. Created a pivot table into a new sheet and named it "reason". Selected [Cause of death] as rows, [ML Number] as values. Sorted the results in descending order.
   (screenshot_cause2)
#### Findings: "Exposure" was the biggest cause of migrant death in Arizona. 

### Q7: What was the maximum age, minimum age and average age of dead migrants in Arizona?
1. Using "=MAX", "=MIN" and "=AVERAGE" functions to calculate numbers in the [Age] column.
   （screenshot_age）
#### Findings: The maximun age of dead migrants was 99; the minimum age was 0, and that referred to three incidents of nonviable fetus (so heartbreaking). The average age was around 31.  



