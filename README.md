# LinkedIn Job Scraping Using Python
This code scrapes job listings and company names from LinkedIn for a specific search query.
This is a Python script that uses Selenium to scrape job listings.

**Features**:

Extracts company names and job titles from search results.
Saves the extracted data as a CSV file (linkedin.csv).
Option to collect job listing URLs (not currently functional).


**Requirements:**

Python 3

Libraries:
- pandas
- selenium
- webdriver_manager (optional).

**Instructions:**

Here's a breakdown of the code and its functionalities:

**1. Import Libraries:**

selenium: Used for web automation to interact with the LinkedIn website.
time: Provides functions to control the script's execution timing.
pandas: Enables data manipulation and creation of DataFrames.
os: Used for interacting with the operating system (potentially for file path management).

**2. Define Target URL:**

The script allows you to set the target URL for the job search. You can modify the url1 variable to include specific keywords, location filters, and other search parameters.

**3. Initialize WebDriver:**

The script uses Selenium's webdriver to launch a Chrome browser instance. You might need to replace the path provided to the chromedriver.exe file with the actual location on your system.

**4. Find Number of Job Listings:**

It retrieves the element containing the total number of jobs displayed on the search results page using its class name and converts the text content to a numeric value using pd.to_numeric.

**5. Infinite Scrolling:**

The script employs a loop to simulate scrolling down the webpage progressively. It utilizes JavaScript's window.scrollTo method to bring more content into view. An exception handler is included to manage potential errors during scrolling.

**6. Extract Company Names and Job Titles:**

It iterates through each job listing on the page and extracts the company name and job title using their respective class names. These are then appended to separate lists named companyname and titlename.

**7. Create DataFrames:**

The script creates two DataFrames: companyfinal for company names and titlefinal for job titles.

**8. Combine DataFrames:**

It merges the two DataFrames (companyfinal and titlefinal) into a single DataFrame named x to have a consolidated record of company names and corresponding job titles.

**9. Save Data to CSV:**

The script saves the final DataFrame x as a CSV file named "linkedin.csv" in your current working directory.

**10. Extract Job Listing URLs (Optional):**

The commented-out section demonstrates how to potentially extract the URLs of each job listing. It finds all elements with the class name base-card__full-link and retrieves their href attributes, which contain the URLs.




