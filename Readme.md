# FoondaMate Coding Challenge
Name: Matthew Craig
Location: Cape Town, South Africa

## How it works
The CLI program was developed in Java.\
It takes in 3 arguments, however, if only the URL is provided, all values will be printed:\
[0] API URL\
[1] Start date of filter - Format is "dd-MM-yyyy"\
[2] End date of filter - Format is "dd-MM-yyyy"

Google's Gson library is used to connect to the API and return a JsonObject.\
From the JsonObject, an array of Map Entries is generated.\
If a start and end date are provided, the array is trimmed to the required date range.\
The results are displayed using unicode block elements.\
Each whole block represents the maximum users/100 (blockVal). The day with the highest users will thus display 100 blocks and all other days will be a fraction of 100.\
For each element (date) in the Map Entry array:
- The date is checked: If a new month or year is reached, a line displaying the updated information is printed. Afterwards (regardless of month or year changes), the day of the month is printed.
- The required number of unicode block elements is printed: A whole block █ is printed users/blockVal times. The remainder from this operation will be matched with the closest fractional block element, which will be printed at the end of the block sequence. Eg. If the remainder is closest to 1/2, then ▍will be displayed.

## How to run the program
This requires the user to have Java installed on their pc.\
Using a terminal, locate the CLIGraph directory.\
Run the jar file using: java -jar CLIGraph.java arg[0] arg[1] arg[2]\
eg. java -jar CLIGraph.jar http://sam-user-activity.eu-west-1.elasticbeanstalk.com/ 01-01-2022 02-01-2022