# US Congressional Colorado Precinct Election Audit & Analysis
--------------------------------------------------------------
### The Board of Elections for Colorado is concerned with certifying and auditing the results from the most recent congressional election. A successful audit will prove that our tabulating methodology will return the same election values and statistics consistently and most importantly, the results can be reproduced by a third party. The methodology, applications, functions and logic used to produce the results are accurate and align with industry standards. The summary and anlysis will provide transparency in our process and provide accountability for our methods in measure with the political significance of ceritfying our results.

# Election-Audit Results: 
## Data Scrubbing and Cleanup
### In order to accurately tabulate the results, the input data first needed to be assessed and assimilated into a comprehensive format. All three ballot return types (mail-in, punch card, and direct reporting electronic) were merged into a CSV (comma separate value) file that is easily maniuplated using the Python programming language. The original data file was found to have no anomolies, discrepancies or missing values and analysis could begin. Below are the results derived from our analysis using python script.

## Final Result Summary

-------------------------
- Total Votes: 369,711
-------------------------

County Votes:
- Jefferson: 10.5% (38,855)
- Denver: 82.8% (306,055)
- Arapahoe: 6.7% (24,801)
-------------------------
- Largest County Turnout: Denver
-------------------------
- Charles Casper Stockham: 23.0% (85,213)
- Diana DeGette: 73.8% (272,892)
- Raymon Anthony Doane: 3.1% (11,606)
-------------------------
- Winner: Diana DeGette
- Winning Vote Count: 272,892
- Winning Percentage: 73.8%
-------------------------

# Methodology
## Identifying, Sorting and Extracting the Data
### The format of data in our CSV file, in python terminology, is a "list of dictionaries" or a list of key, value pairs. Within our chosen programming language, there are many powerful tools to extract data from dictionaries in order to sorth through our list using specific identifiers. These values can be assigned to variables that can then be manipulated to use for further analysis.
### In the dataset there are three sets of key, value pairs in each "dictionary". The column header functions as the "key" and the corresponding data in the cell functinos as the value. In our first line of data the dictionary is as follows {"Ballot ID":1323913, "County":Jefferson, "Candidate":"Charles Casper Stockham"}. From here we can use a few simple built in funcations within Python to identify the "key" we want to sort by and perform analysis.

## Manipulating and Expressing Data Through Python Functions: For Loops & Conditionals
### Our first order of operations is to sort through the rows and identify each row as a single vote to acquire the "total" vote count. A simple "for loop" that runs through each dictionary with a function that iterates and summates for every entry. Within of our original "for loop" we can use conditional statements to create parameters to identify unique candidate names and county names and tabulate votes for each variable.

### Once our baseline numbers are tabulated (total votes, votes per candidate, votes per county), we can use the variables holding these values to perform mathematical functions. From the total vote counts, and vote counts by candidate, we can find percentage of vote by candidate by dividing the later by the former and multiplying by 100. The same mathematical algorithm can be used with the variables for total vote and county vote to find vote participating by county.

image of mathematical funcitons

### Once total votes, total votes per candidate and percentage of votes is returned, we can run a simple conditional statement to determine which candidate has the winning amount of votes and percentage of votes as seen below. This code uses conditional statements to create paramters that if met, logically return our winning candidate. 

image of conditional to determine winning candidate

# Election Audit Challenges and Recommendations
## Model for Future Election Analysis & Challenges with Current Script
### To reduce institutional redundancy, with a few minor modifications to the script, the funcationality could be expanded to audit election results for future analysis. With a few minor edits, the range of application for this script could be greatly expanded. The first limitation to consider is the code language used to loop through our list of dictionaries - these opening lines of code require a specific sequential organization of the data - the for loops call upon the values in the dictionary through indices essentially requiring Ballot ID to always be located in column 1, County name to always be located in column 2 etc. The script would be much more versatile if instead the first for loop identified the "key" terms in the header row(column header values) to find where specific lists of data were located. In this way time and energy would not be spent reformatting raw data files on the front end.

image of for loop calling on column header values by index

### The second limitation to consider is the code's prescriptive use of language -  currently it can only reasonably be used for elections where results are tabulated on the county level. If the Colorado and/or Congressional Board wanted to audt and certify results on elections based on different geographies (zipcodes, cities) the output format would hinder readability. With minor changes to the language used in declaring variables and outputing language, the script could become more adaptable and functional for any election analysis in the future.

### Lastly, the python script can be refactored to accept generic csv files that are not hard coded.

## Further Recommendations
### The results about county turnout would be more compelling when compared to county population. A data point about participation rates based on votes compared to population might be more informative for decision making at the campaign level. Use of pandas and other visual tools to incorporate visual analysis of maps would be warranted as well. 

