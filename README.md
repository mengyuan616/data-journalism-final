# J296 FInal: A data story about migrant deaths at the U.S.-Mexico border
By Mengyuan Dong <br><br>

## Dataset 1
### Data source:
* International Organization for Migration(IOM) https://missingmigrants.iom.int/downloads


### First Steps:
1. **Cleaning the data**. I was looking at the IOM data first. There were 10275 rows in total. After inspection, the data was very normalized and didn't require much refining, and there were no duplicates found. So I could start the analyzing process in Google Sheets.
2. **Opening the data in Google Sheets**. I made a copy of the dataset, froze the first row and made it bold.

### Q1: How many migrant deaths occurred at the U.S.-Mexico border? At which regions did the incidents happen?
Step-by-step answer:

1. Applied filter to the [Migration route] column, and selected "US-Mexico border crossing" only. 
   (screenshot-region column)
2. Made a new sheet and pasted all incidents at the U.S.-Mexico border. There were 2698 incidents in the dataset. 
3. Made a pivot table into a new sheet and named it "Year". Selected [Incident year] as rows, and [number of dead] as values, and [Region of incident] as columns. 
   (screenshot-year)
#### Findings: The number of cases have been increasing each year, and 2021 has seen 714 incidents, the highest on record. About 83% of those incidents happened in the U.S. territory

### Q2: Which U.S. states had most migrant deaths?
Step-by-step answer: 

1. As the dataset only had coordinates, I had to use geocodio to convert coordinates into addresses. 
2. In column [Coordinates], the data format looked like this: POINT (-110.366453 31.650259). I used "SPLIT" function to split this into latitude and longitude, which made it easier for geocoding. 
(**There were 44 incidents that didn't have location information**)
3. Copied and Pasted the results into a new sheet called "long&lat", there were 2654 results in total. 
4. Downloaded sheet "long&lat" as a csv file, and uploaded it onto Geocodio. 2,502 out of 2,653 locations were geocoded successfully.
5. Created a pivot table into a new sheet and named it "state". Selected [States] as rows, and [Main ID] and [Number of Dead] as values.
   （screenshot_year）
#### Findings: Arizona had most incidents, and Texas had the highest number of deaths. (There might be more than one death in some incidents)

### Q3: How many dead migrants were men? And how many were women?
1. Created a pivot table into a new sheet and named it "gender". Selected [Incident year] as rows, and [Number of females] and [Number of males] as values.
   (screenshot_gender)
#### Findings: There were more male dead than female each year. 

### Q4: What were some major causes of death?
1. Created a pivot table into a new sheet and named it "cause". Selected [Cause of death] as rows, [Number of dead] as values, and [Region of Incident] as columns.
2. For values, chose "show as % of grant total"; for rows, chose "sort by number of dead" in descending order.
   (screenshot_cause)
#### Findings: For incidents happened in Central America, the primary reason for death was "drowning"; while for those happened in North America, the primary reason was "harsh environmental conditions".


## Dataset 2
* Humane Borders & Pima County Medical Examiner’s Office https://humaneborders.info/app/map.asp


