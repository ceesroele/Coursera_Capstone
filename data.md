# Data

## Source
FourSquare is a location data company.  Its website can be found at https://foursquare.com/

The company writes on itself:

> Our human-sourced database of 105 million places provides the richest index of venue information—from ratings and reviews to tips and tastes, our data paints an intricate story of place.

The FourSquare service allows developers to obtain data about locations world wide. This can include pictures, number of people who have checked into that location, reviews, and ratings.

Currently, we are interested in restaurants. The data made available by FourSquare, includes the following fields which we are interested in:

|Field|Description|
|-----|-----------|
|id|unique identifier for venues, e.g. "5284cb6511d2e6ccc1a464f3"|
|name|name of the venue, e.g. "Rijksmuseum Café"|
|category::name|name of the FourSquare category of the venue, e.g. "Italian Restaurant"|
|location::latitude|float identifying the venue's latitude|
|location::longitude|float identifying the venue's longitude|

In the table above the "::" denotes that the right hand side is an attribute of the attribute on the left hand side.

## Selection of data
Methodology, to be discussed later, in the full report, is based on comparing data from different cities. As we have taken our starting point from the growth of the number of tourists, we will first identify a number of touristic venues spread over Europe. We take as our beginning museums as they are a kind of venue that is present in many cities.

An overview of museums was found by looking at a number of travel blogs and manually adding latitude/longitude coordinates using the Nominatim geolocation service on the address of each museum.

We select data from the FourSquare service as follows:
* Query FourSquare for venues within a certain **radius** of the museum which we have taken as a basis for search.
* Query FourSquare for venues **falling under the top level category “Food”**, which is the category under which restaurants fall.

## Filtering of data
After receiving the data from the FourSquare Service, we filter the result to only include those venues with the word “Restaurant” in the category, so as to filter out e.g. coffeeshops, wine bars, and foodstands.

## How will this data serve to answer our question?
Remember that we try to answer the question: **What kind of food served is relatively likely to make a restaurant successful in Riga?**

The selected data will allow us to compare the composition of restaurant categories among those venues near museums in different cities. Where the composition of restaurant types is relatively similar, we look at what restaurant categories in Riga are underrepresented. Based on the experience of other cities where restaurant customers turn out to have similar tastes, those underrepresented categories of restaurants are relatively likely to have a market in Riga and hence become successful.