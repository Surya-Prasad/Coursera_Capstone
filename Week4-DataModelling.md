## Data Modelling

#### The Data
The target for our analysis is the Metropolitan City Chennai, the Capital of Tamil Nadu, India. The reason for choosing this target is because firstly, Chennai is a growing metropolitan, and is hence is guaranteed to have a healthy presence and lack of venues alike. Some areas might be rich in some trades, and other areas lacking. Also, Chennai being one of the larger cities, the data exists.

#### The Source
The data is collected from (Wikipedia)[https://en.wikipedia.org/wiki/Category:Suburbs_of_Chennai] and the locations are extracted by geopy, a python package that is popular for it's functionality. BeautifulSoup and Urllib is used to scrape the page. 

#### The API
The FourSquare API is used for the purpose of venue extraction. A Developer account is used to extract regular calls.