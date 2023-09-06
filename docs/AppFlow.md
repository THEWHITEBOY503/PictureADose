# Main flow
## This features an outline of the planned flow for the main request, from image capture to completion

### Image classification
First, the user presses the camera button and captures an image. Let's use this picture as an example.
![Image](https://c8.alamy.com/comp/MDNGMX/kaliningrad-russia-circa-october-2017-food-served-on-a-tray-at-mcdonalds-restaurant-MDNGMX.jpg)
The image is sent to a computer vision engine with an AI image recognition model attached to it. A potential program I'm considering building this project off of is [lannguyen0910's food-recognition repository.](https://github.com/lannguyen0910/food-recognition) Here's an example from the repository:
![Image](https://github.com/lannguyen0910/food-recognition/blob/master/static/assets/demo/5.jpg)

I haven't set this up or dug into the code yet, but if I'm lucky, I would take all the food items recognized by the app (I'll probably filter the results by anything with a prediction score of 65% or higher) and put them in a list (most likely handled in JSON).
Anyways, the AI model comes back with a list of food items. If the user opts to make a GPS request, Picture A Dose will then use GPS to extract the name of the nearest POI within a very close proximity, in hopes that it would extract the name of the place where the user is. If a name is extracted from the GPS, it gets appended to the beginning of each food item name in the list, so in our example we would get the results "McDonalds Cheeseburger" and "McDonalds Fries". (The model won't be trained to recognize drinks, so the coffee is excluded) If not, it proceeds with just the food name. It's worth noting that these may be too vague or incorrect compared to the actual food name [Ex: A Big Mac being recognized as a cheeseburger]. This can be mitigated by training the model on specfic foods with their name, so a separate recognition for a Big Mac burger. Of course, this isn't perfect and may lead in inaccuracies, so I'm eager to experiment with it and see how accurate it is. 
### Gathering nutrition info
Once the JSON list with the names of all the food items is made, a script will make a request to a nutrition API or database (online / offline) for each item on the list. As each item gets a request, it comes back and updates the JSON list, until all items in the list have nutrition info. 
### Calculating insulin dosage
Now that there is a record of all of the food items in the picture and their nutrition info, we need to calculate an insulin dosage. When the user starts the app for the first time, they will be prompted to add in their insulin:carb ratios (with time periods available too for people whose I:C changes throughout the day). With all the nutrition info gathered, a script will total up the carbohydrates of all the food items, then divide it by whatever the I:C ratio for the current time is. 

## That's it! 
