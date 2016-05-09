Data
==============================================================================================================

Step 1: Download three data set files in CSV format from two websites
---------------------------------------------------------------------------
Navigate to the following link: http://www.bls.gov/lau/tables.htm
Scroll down to find labor force data by county for the years 2000 and 2010
Download each file and covert file extension to CSV format
Now that we have our employment or labor force data sets, we can navigate to the following link and download our 2010 Census population data set: www.census.gov/population/www/cen2010/cph-t/cph-t.html
Select the first option in the table titled “Population Change for Counties in the United States and for Municipios in Puerto Rico: 2000 to 2010”
After selecting the link you will be directed to the page below where you can download the file using Excel and save in CSV format


Step 2: Cleaning raw data sets and adding FIPS Code
--------------------------------------------------------------------------
Now that we have downloaded and gathered our data, we are able to begin cleaning and processing it so that it will be able to interact efficiently with our other systems. Begin by removing unnecessary column headers or potentially merged fields from the 2010 Census population data set
Replace with usable column headers
Now we need to remove the unnecessary column headers from our 2000 labor force data set
Replace with usable column headers
Repeat numbers 3 & 4 with 2010 labor force data set
Now that we have cleaned up our column headers, we need to create a usable FIPS Code in all three data sets in order for our data to interact successfully with the visualization software we will be using
Fortunately, our two labor force data sets included a State FIPS Code and a County FIPS Code. However, this information is not formatted correctly for our needs. The County FIPS Code should be a 3-digit number containing leading zeroes when necessary. The State FIPS Code should be a 2-digit number containing a leading zero when necessary. These two fields (State FIPS Code, County FIPS Code) should be concatenated into one single FIPS Code that will be used spatially to identify distinct geographic regions for visualization. As an example, if we have a County FIPS Code of 1 and a State FIPS Code of 1, our usable FIPS Code will be “01001”. After formatting the columns to the correct data type to include leading zeroes and concatenating the two fields, we have created our usable FIPS Code
Next we need to be sure that our newly created FIPS Code is included in our other two data sets. We realize that the only common information in our data sets are the county name and state field. In our population data set we need to convert the state name (Ex. “Alabama”) to the correct state abbreviation (Ex. “AL”). By concatenating the county name and state abbreviation in our population data set, we are able to establish a similar format that exists in our labor force data sets. We can trim these fields in order to make sure there are no leading or trailing spaces that would differentiate a county record in one of the data sets. Now that we have obtained a like field in all of our data sets, this field can be used with a matching function to index in our FIPS Code for each record. Using the indexing function we are able to successfully incorporate our FIPS Code into all three of our data sets.
Step 3: Removing unlike records from Population data set

Step 3: Data Cleaning
----------------------------------------------------------------------------
When incorporating our FIPS Code we realize that two county records do not exist in our labor force data sets, but were listed in our population data set. After considering the population change and values for these two records and determining that they were relatively small and less significant, we opted to remove them from our population data set so that our records were consistent across the board. These records are listed below for reference. County State Year 2000 Year 2010 Number Change Percent Difference Kalawao County Hawaii 147 90 -57 -38.8 Bedford city Virginia 6,299 6,222 -77 -1.2

Now that we have downloaded our data sets, removed unnecessary column headers, incorporated our usable FIPS Code, and removed unlike records from our data sets, we consider our data “cleaned” and proceed with the project.