# Construct experimental datasets


The 1-order, 2-order, and 3-order datasets used in the experiment are built based on the application invoked API, for example, there is a application, and its invoked API is shown in the following table

application| invoked API
-------- | -----
LocEight DATA| Flickr, Google AdWords, Google Maps, GeoNames

Based on the above application, we can build datasets for 1-, 2-, and 3-order dataset, as shown in the following table


1-order dataset|
---- | 
(Flickr) -> (Google AdWords, Google Maps, GeoNames)
(Google AdWords) -> (Flickr, Google Maps, GeoNames)
(Google Maps) -> (Flickr, Google AdWords, GeoNames)
(GeoNames) -> (Flickr, Google AdWords, Google Maps)

2-order dataset|
---- | 
( Flickr, Google AdWords) -> (Google Maps, GeoNames)
( Flickr, Google Maps) -> ( Google AdWords, GeoNames)
( Flickr, GeoNames) -> ( Google AdWords, Google Maps)
( Google AdWords, Google Maps) -> (Flickr, GeoNames)
( Google AdWords, GeoNames) -> (Flickr, Google Maps)
( Google Maps, GeoNames) -> (Flickr, Google AdWords)

3-order dataset|
---- | 
(Flickr, Google AdWords, Google Maps) -> (GeoNames)
(Google AdWords, Google Maps, GeoNames) -> (Flickr)
(Flickr, Google Maps, GeoNames) -> (Google AdWords)
(Flickr, Google AdWords, GeoNames) -> (Google Maps)

If all application are processed along these lines based on their invoked APIs, you end up with all the datasets for 1-, 2-, and 3-order recommendations.
