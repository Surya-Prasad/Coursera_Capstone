## Report

### Introduction

##### Why would you need this project?
One of the main problems for aspiring shopowners in growing metropolitan cities is the need to search for market. Availability is one major factor in deciding if a business is to be successful or not. Manually scouring major competitions, tallying the different stores and such is _tiring_ to the individual. Hence, it would be prudent to automate this using available data, and get a meaningful result out of it.

##### The API 
The Foursquare API can be utilized to acquire the venue data, given the location. So, putting two and two together, We can build a Clustering Algorithm that can group places with similar vacancies together and give out lists of places that our potential shopowner can then capitalize on. A top 10 list would be precise and crisp.

##### The Target
Here, the target audience is anyone who wants a group of venues similar to the venue that they've queried. This could be small businesses, large corps looking to expand, food chains, or an evening jogger looking for a change of pace, but in similar surroundings. 

### Data

<p align="center">
    <img src='./Images/Chennai.jpeg' class="center">
    <br>
    Chennai
</p>

##### The Data
The target for our analysis is the Metropolitan City Chennai, the Capital of Tamil Nadu, India. The reason for choosing this target is because firstly, Chennai is a growing metropolitan, and is hence is guaranteed to have a healthy presence and lack of venues alike. Some areas might be rich in some trades, and other areas lacking. Also, Chennai being one of the larger cities, the data exists.

##### The Source
The data is collected from ![Wikipedia](https://en.wikipedia.org/wiki/Category:Suburbs_of_Chennai) and the locations are extracted by geopy, a python package that is popular for it's functionality. BeautifulSoup and Urllib is used to scrape the page. 

##### The API
The FourSquare API is used for the purpose of venue extraction. A Developer account is used to extract regular calls.

### Methodology

##### Data Preprocessing
After scraping the page with BeautifulSoup, the result was then iterated over, and the text elements were appended on to a DataFrame, creating a structure of the existing suburbs that we could work with. Using this DataFrame, the locations were queried on geopy, extracting the latitude and longitude information onto the DataFrame.

##### Using the FourSquare API
We feed in our Subruban Neighbourhood, it's latitude and longitude, and repeat until we have a list of venues for each Neighbourhood. Now Chennai has a lot of overlapping suburban areas, and hence, we remove the redundant ones. This has to be done manually, as if this were to be fed in, we would get two pts at the same location. Helpfully, the API returns VenueTypes, and this would help us in identifying what sort of services were provided at that location. 

##### Filtering out the user-requested services from the DataFrame
My approach to this was to create a user-interactive window that gets his input and maps it to the existing VenueTypes. Any clashes, and I'd request the user to further specify their choice, after narrowing down the results based on the previous query. (For instance, 'Restaurant' would be too vague, in which case the different restaurants would be displayed before the user selects 'Persian Restaurant')

We need to filter out the requested venue out of the lot. The approach used here is to One-Hot encode the VenueTypes (convert the categorical to numeric data) and to take the mean of the same. Now, our data is ready for the model.

##### The Model
We need to take up a clustering approach, as we are not sure of the underlying patterns that the venues exhibit. Also, it is imperative that we do not feed the latitudes and longitudes into the Clustering Model, as it would cluster them based on location. Hence the data is put into a new DataFrame, with only the encoded values. 

The clustering itself is done by K-Means Clustering, as the dataset is small, and Euclidean distance would do as the distance metric. The value for K is tested with the error, and a value of 4 is decided upon as the suitable number of clusters. We then fit the model, obtain the clusters, and append them onto the Dataframe, based on which, we can further visualize the clusters.

### Results
The results (Clusters) are displayed on a map, with the aid of the Folium Library. The most desired locations are marked with a red marker. A top 10 list is also generated. 

### Discussion
Even though availabiliy of competition is not the only factor in determining the best location to start up business, it is a start. Chennai does not have extensive information about the preferences of people in a demographic, and hence, metrics like these provide an idea for where to look.

### Conclusion
Even though metrics like these are, to a large extent, too vague to be completely relied on to use in a business venture, they definitely are of a huge help to eliminate places which already have a service available. The user benefits hugely from this, and can utilize his resources and time better, in his search. 

If we were to improve on this, we would require data for the different preferences of people, such as distance, consumption levels and such. But that is beyond the scope of this project, but exists, nonetheless. 

Thanks for your interest!