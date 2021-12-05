# Analysis of Election Results

## 1 Overview of Project

This project was the third challenge in the Carleton University Business Analytics and Data Visualization Boot Camp.  Module 3 of the boot camp was intended to help us, through the use of Python, build a foundation in programming and learn how to access, process, manipulate and store data.  The project involved the use of pseudo code to build the logical structure of the analysis and then to code in Python to complete the project objectives.

### 1.1 Purpose

The purpose of the specific project within this module was to assist a Colorado Board of Elections employee, Tom.  He will be conducting an election audit of the tabulated election results for a US congressional precinct .  This is typically performed in Excel, but Tom's boss Seth, wants to know if it can be automated using Python.  We were provided with pseudo code that assessed a few of the required results and we were asked to complete the program and provide a complete analysis of the results.

### 1.2 Approach

Working with a large data file of ballots, election_results.csv, the basis of the analysis was to extract candidate and county names and add them to lists that can then be used to enumerate the ballots.  To convert the csv file, we opened it and read it into a variable "reader" using the csv function csv.reader(), which stores the file into a Python object.  This capability was made possible by importing the csv module which implements classes to read and write tabular data in csv format.  In Figure 1.1 you can see how the file is read and we extract its header by reading the first row of election_data into a variable "header".

![This is a VS screenshot of the PyPoll.py code](Resources/Reading_Header.png "Figure 1.1 - Reading the csv file header")  
**Figure 1.1 - Reading the csv file header**

The next step was to loop through the data rows of reader to extract candidate and county names from the appropriate column in the row of data as shown in figure 1.2 below.

![This is a VS screenshot of the PyPoll.py code](Resources/Loop_Through_Rows.png "Figure 1.2 - Looping Through Data Rows")  
**Figure 1.2 - Looping through data rows**

In figure 1.3 you can see that we are extracting a unique list of candidates, and also enumerating information from the individual ballots and adding them to the candidate votes dictionary.

![This is a VS screenshot of the PyPoll.py code](Resources/Extract_Unique_Candidates.png "Figure 1.3 - Building Candidate List and Candidate Vote Dictionary")  
**Figure 1.3 - Building Candidate List and Candidate Vote Dictionary**

In a similar fashion, in figure 1.4 you can see that we are extracting a unique list of county names, and also enumerating the information from the individual ballots and adding them to the county votes dictionary.

![This is a VS screenshot of the PyPoll.py code](Resources/Extract_Unique_Counties.png "Figure 1.4 - Building County List and County Vote Dictionary")  
**Figure 1.4 - Building County List and County Vote Dictionary**

In figure 1.5 we check the total votes cast for all candidates against the total votes cast in all counties.  These numbers, by definition, should match, so if they do not then an error has occurred and the code and/or data would then need to be checked for a cause.

![This is a VS screenshot of the PyPoll.py code](Resources/Data_Cross_Check_Validation.png "Figure 1.5 - Cross Checking the Total Vote Count")  
**Figure 1.5 - Cross Checking the Total Vote Count**

The last and most important part was to output the results both to the screen as well as a text file.  The code for this is shown in figure 1.6, it includes another class from the csv library that facilitates writing to a text file.

![This is a VS screenshot of the PyPoll.py code](Resources/Outputting_Results.png "Figure 1.6 - Writing the Results to the Screen and a File")  
**Figure 1.6 - Writing the Results to the Screen and a File**

### 1.3 Challenges

There were a few challenges in working on this project and they occurred because I have, in my career, used much older programming languages like Fortran.  We also just completed a unit using Visual Basic scripts in macro enabled Excel spreadsheets.  This was my first time working with Python and as a result here is the list of the issues that I faced:

- The biggest challenge was the fact that Python is so very dependent on indentation to determine the end of loops and conditional branches - instead of a very clear end statement.   A great amount of attention was required to make sure that the code was being read as I intended it to be.
- Capitalization (or should I say non-capitalization) for key words - "**for** example **For**".  Again I had to make sure the statements were being evaluated as the expected code.
- Python has a large number of available coding methods and libraries that can make your life very easy, but the challenge is finding out what is available.  Reviewing lots of other code helps expose you to some new efficiencies, like the use of x += 1 can replace x = x + 1, very simple and very useful indeed. 

## 2 Analysis and Observations
### 2.1 Audit of the Election Results

Figure 2.1 below was captured using the "Save as Image" right click feature in GitBash.  This is the screen presentation of the election results.

![This is a image capture from GitBash running](Resources/Election_Results_GitBash.png "Figure 2.1 - Election Results as View on Screens")  
**Figure 2.1 - Election Results as View on Screens**

The results of the election were also written to a text file, "election_analysis.txt".   Figure 2.2 is a screen shot of that file when opened in Notepad.

![This is a screen shot from a Notepad view for the file](Resources/Election_Results_Text_File.png "Figure 2.2 - Election Results as Written to a Text File")  
**Figure 2.2 - Election Results as Written to a Text File**

The program correctly captures the required data and displays it clearly both directly on the screen and in the required text file format. 

### 2.2 Observations

The first important observation is that the sum of the ballots equals 369,711 when counted by ballots from a county or ballots for a given candidate.  It is important to confirm the validity of the results by appropriately cross checking the data for the possibility of errors.  As illustrated in the approach section above, see figure 1.5, our program would have displayed an error message if these two methods resulted in a different count of total ballots.

#### 2.2.1 Review of County Data

The results did show that at 82.8% of the county votes, Denver contributed to the vast majority of the votes.   This is a very surprising result since Jefferson, Denver, and Arapahoe are among the largest counties in Colorado with reasonably comparable populations.  I am concerned that not all of the ballots are represented in the data that has been provided for audit.  I recommend that the data source be thoroughly reviewed for missing ballot sources.

#### 2.2.2 Review of Candidate Data

The results did show that Diana DeGette was determined to have been the winner with an overwhelming 73.8% of the total votes counted.  Unfortunately, based on the county data findings in section 2.2.1 it would not be possible to certify the results until such time as the county based missing ballot issue has been resolved.

#### 2.2.3 Summary of Election Outcomes

In summary this is what has been determined from the election data analyzed:

- The total votes cast, based on counting either the candidate that was selected or the county in which the ballot came from, was 369,711 confirming that the data has been validated.
- The largest number of votes came from Denver county with 306, 055 votes accounting for 82.8% of all votes
- The county vote count is verified by the fact that the total votes by county add to 369,711 and the percentages add to 100%
- The largest vote count by candidate goes to Diana DeGette with 272,892 votes accounting for 73.8% of the votes
- The candidate vote count is verified by the fact that the total votes by candidate add to 369,711 and the percentages add to 100%

### 2.3 Overview of Analysis
#### What do we know?  
Elections are very important as they affect the future of all citizens and they, therefore, need to represent everyone who has cast a ballot: 
- What we do know is that the Python program works effectively and without error.  
- We also know that there appears to be missing data sources that are not in the data that has been provided.

#### What don't we know?
As is often the case there is always going to be more information required:
- First of all, we don't know the history of this data - maybe it is very old and Denver was way bigger than the other counties at that time 
- We also don't know if maybe we are just analyzing test data to see if we really would be able to find data discrepancies 

#### How can we help?  
It is my opinion that Tom's boss, Seth, was just trying to see how well the Python file would work, and I would have to say that we passed the test.    It is apparent that Seth is a forward thinking man and is likely looking to get a bigger job within the state of Colorado.   I think what we have to do to help him with his goal is:

- Ask him for a complete set of data so that we can prove that the program will work on a much larger data set.
- Prepare a detailed briefing to assist Seth when pitching a statewide audit system that he would be in charge of.

I would recommend that Tom further engage my consulting services to determine if, through the analysis of more information, the auditing capability can be enhanced.  Knowing what percentage of county votes went to a particular candidate, for example, may be of value in determining other voting irregularities.  

Here are two clear uses of the application that Seth could propose to the election commission:

- The first application is to analyze data at a more granular level, for example the county votes are derived from a number of election polling stations.  Collecting polling station data and comparing it to all expected polling stations in a given county would help validate the integrity of the data analyzed.
- The second application would be to analyze the data across the entire state.  Since we know that Colorado consists of a much greater number of counties than the three extracted from the data we currently have, we could easily modify the  application to identify missing counties by comparing the extracted county list against a list of expected counties.

### 3.0 Repository Navigation

This section of the report in intended to help the reader locate the applicable folders and files that have been used to develop this report.

#### 3.1 Repository Home

In the home repository you will find, this README file, a ZIP file of the entire repository and most importantly the PyPoll.py program that has been developed to analyze the election data.

#### 3.1 Resources Folder

Within the Home Repository you will also find a folder called "Resources" that contains the following files:

- The original raw election data in the file "election_results.csv"
- Eight PNG files that are image files of the figures that are referenced throughout this report

#### 3.2 Analysis Folder

The "analysis" folder is also a subfolder of the Home Repository.  It contains the text file output of the analysis called "election_analysis.txt".



