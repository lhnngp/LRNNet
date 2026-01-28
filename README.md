# Instruction
To run the project, simply execute the main.py file.

Before running the code, please make sure that all required dependencies are installed and that the dataset files are placed in the correct directory as expected by the dataloader.


# Component
- dataloader.py: Responsible for data loading and preprocessing.
- main.py: The main entry point of the project.
- metrics.py: Contains the evaluation metrics used in the project.
- models.py: Defines the neural network architecture used in the project.
- utils.py: Contains utility functions used in the project.
- train-queries.pkl, train-answers.pkl: Traing set.
- valid-queries.pkl, valid-answers.pkl: Validation set.
- test-queries.pkl, test-answers.pkl: Test set.

# Experimental Dataset Construction

The datasets used for 1-order, 2-order, and 3-order recommendation are constructed based on the cloud API invocation information of mashups.

For example, given a mashup and the cloud APIs it invokes as shown below:

| Mashup        | Invoked cloud APIs |
|----| -- |
| TravelAssist  |Twitter, OpenWeather, Google Maps, Yelp|

Based on this mashup, we can construct datasets for 1-order, 2-order, and 3-order recommendation as follows.

| 1-order Recommendation Dataset               |
|----------------------------------------------|
| (Twitter) → (OpenWeather, Google Maps, Yelp) |
| (OpenWeather) → (Twitter, Google Maps, Yelp) |
| (Google Maps) → (Twitter, OpenWeather, Yelp) |
| (Yelp) → (Twitter, OpenWeather, Google Maps) |

| 2-order Recommendation Dataset                |
|-----------------------------------------------|
| (Twitter, OpenWeather) → (Google Maps, Yelp)  |
| (Twitter, Google Maps) → (OpenWeather, Yelp)  |
| (Twitter, Yelp) → (OpenWeather, Google Maps)  |
| (OpenWeather, Google Maps) → (Twitter, Yelp)  |
| (OpenWeather, Yelp) → (Twitter, Google Maps)  |
| (Google Maps, Yelp) → (Twitter, OpenWeather)  |

| 3-order Recommendation Dataset               |
|----------------------------------------------|
| (Twitter, OpenWeather, Google Maps) → (Yelp) |
| (OpenWeather, Google Maps, Yelp) → (Twitter) |
| (Twitter, Google Maps, Yelp) → (OpenWeather) |
| (Twitter, OpenWeather, Yelp) → (Google Maps) |
