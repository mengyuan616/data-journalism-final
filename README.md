# J296 FInal: A data story about migrant deaths at the U.S.-Mexico border
By Mengyuan Dong <br><br>

## Data Analysis
### Data source:
* International Organization for Migration(IOM) https://missingmigrants.iom.int/downloads
* Humane Borders & Pima County Medical Examiner’s Office https://humaneborders.info/app/map.asp

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
**The Result shows that the number of cases have been increasing each year, and 2021 has seen 714 incidents, the highest on record. About 83% of those incidents happened in the U.S. territory** 

### Q2: Which U.S. states had most migrant deaths?
Step-by-step answer: 

1. As the dataset only had coordinates, I had to use geocodio to convert coordinates into addresses. 
2. In column [Coordinates], the data format looked like this: POINT (-110.366453 31.650259). I used "SPLIT" function to split this into latitude and longitude, which made it easier for geocoding. 
(**There were 44 incidents that didn't have location information**)
3. Copied and Pasted the results into a new sheet called "long&lat", there were 2654 results in total. 
4. Downloaded sheet "long&lat" as a csv file, and uploaded it onto Geocodio. 2,502 out of 2,653 locations were geocoded successfully.
5. 







