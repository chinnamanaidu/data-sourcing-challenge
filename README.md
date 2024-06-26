#### data-sourcing-challenge

# PART 1
#### Dependencies
#### Set environment variables from the .env in the local environment
#### Set the base URL
url = "https://api.nytimes.com/svc/search/v2/articlesearch.json?"

#### Filter for movie reviews with "love" in the headline
#### section_name should be "Movies"
#### type_of_material should be "Review"
filter_query = 'section_name:"Movies" AND type_of_material:"Review" AND headline:"love"'

#### Use a sort filter, sort by newest
sort = "newest"

#### Select the following fields to return:
#### headline, web_url, snippet, source, keywords, pub_date, byline, word_count
field_list = "headline,web_url,snippet,source,keywords,pub_date,byline,word_count"

#### Search for reviews published between a begin and end date
begin_date = "20130101"
end_date = "20230531"

#### Build URL
#### Create an empty list to store the reviews


#### loop through pages 0-19

#### create query with a page number
#### API results show 10 articles at a time


#### Make a "GET" request and retrieve the JSON


#### Add a twelve second interval between queries to stay within API query limits


#### Try and save the reviews to the reviews_list

#### loop through the reviews["response"]["docs"] and append each review to the list

#### Print the page that was just retrieved
#### Preview the first 5 results in JSON format
#### Use json.dumps with argument indent=4 to format data
#### Convert reviews_list to a Pandas DataFrame using json_normalize()
#### Extract the title from the "headline.main" column and
#### save it to a new column "title"
#### Title is between unicode characters \u2018 and \u2019. 
#### End string should include " Review" to avoid cutting title early
#### Create a list from the "title" column using to_list()
#### These titles will be used in the query for The Movie Database

# Part2
#### Access The Movie Database API
#### Prepare The Movie Database query

#### Print the page number that had no results then break from the loop
#### Create an empty list to store the results


#### Create a request counter to sleep the requests after a multiple
#### of 50 requests


#### Loop through the titles

#### Check if we need to sleep before making a request


#### Add 1 to the request counter


#### Perform a "GET" request for The Movie Database


#### Include a try clause to search for the full movie details.
#### Use the except clause to print out a statement if a movie
#### is not found.

#### Get movie id


#### Make a request for a the full movie details


#### Execute "GET" request with url


#### Extract the genre names into a list


#### Extract the spoken_languages' English name into a list


#### Extract the production_countries' name into a list


#### Add the relevant data to a dictionary and
#### append it to the tmdb_movies_list list


#### Print out the title that was found
        
#### Preview the first 5 results in JSON format
#### Use json.dumps with argument indent=4 to format data

# Part 3

#### Merge the New York Times reviews and TMDB DataFrames on title
#### Remove list brackets and quotation marks on the columns containing lists
#### Create a list of the columns that need fixing


#### Create a list of characters to remove


#### Loop through the list of columns to fix

#### Convert the column to type 'str'


#### Loop through characters to remove


#### Display the fixed DataFrame
#### Export data to CSV without the index
