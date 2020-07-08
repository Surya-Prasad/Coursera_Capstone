## Report

### Introduction

##### Why would you need this project?
One of the main problems for aspiring shopowners in growing metropolitan cities is the need to search for market. Availability is one major factor in deciding if a business is to be successful or not. Manually scouring major competitions, tallying the different stores and such is _tiring_ to the individual. Hence, it would be prudent to automate this using available data, and get a meaningful result out of it.

##### The API 
The Foursquare API can be utilized to acquire the venue data, given the location. So, putting two and two together, We can build a Clustering Algorithm that can group places with similar vacancies together and give out lists of places that our potential shopowner can then capitalize on. A top 10 list would be precise and crisp.

##### The Target
Here, the target audience is anyone who wants a group of venues similar to the venue that they've queried. This could be small businesses, large corps looking to expand, food chains, or an evening jogger looking for a change of pace, but in similar surroundings. 

### Data

![image info](./Images/Chennai.jpeg)

##### The Data
The target for our analysis is the Metropolitan City Chennai, the Capital of Tamil Nadu, India. The reason for choosing this target is because firstly, Chennai is a growing metropolitan, and is hence is guaranteed to have a healthy presence and lack of venues alike. Some areas might be rich in some trades, and other areas lacking. Also, Chennai being one of the larger cities, the data exists.

##### The Source
The data is collected from ![Wikipedia](https://en.wikipedia.org/wiki/Category:Suburbs_of_Chennai) and the locations are extracted by geopy, a python package that is popular for it's functionality. BeautifulSoup and Urllib is used to scrape the page. 

##### The API
The FourSquare API is used for the purpose of venue extraction. A Developer account is used to extract regular calls.

### 