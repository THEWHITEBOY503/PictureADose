# 🚧 UNDER CONSTRUCTION 🚧
This project is in its infancy, and as such has limited information and no working code. This repository serves to publicly keep track of this app's progress and roadmap.

# PictureADose
## What is Picture A Dose?
Picture A Dose is an app I thought up while attending Camp Sweeney. Getting ideas from my [TM-ImageClassifier](https://github.com/THEWHITEBOY503/TM-ImageClassifier) and [NutriMind](https://github.com/THEWHITEBOY503/NutriMind) projects, this app would take a picture of your plate, use an AI model to classify the different food items on your plate, use GPS to narrow down where you're eating, make an API requeast to retreive the nutrition information, add up all the carb information and calculate an insulin dosage using pre-programmed insulin-to-carb ratios. 

## How will it work?
For more info, see our documentation on [the flow of the app.](https://github.com/THEWHITEBOY503/PictureADose/blob/main/docs/AppFlow.md)
In summary, Picture A Dose will use Computer Vision and an AI model trained off pictures of foods, as well as an optional GPS poll to get the name of a restaurant, then combines the resteraunt name and food item (Example: A picture of a chicken sandwich from Chic-Fil-A is classified as a chicken sandwich, but the GPS tells the app you're at Chic-Fil-A, so the request becomes 'Chic-Fil-A chicken sandwich') and makes a request to a nutrition API (or database) to gather nutrition information. I plan to make/use a model that is able to identify several objects in one photo, so for every object it detects, it makes an entry in a list, then adds the restaurant name to each item in the list and makes a request for each item in the list. 


## Progress updates
### July 16th: Uploading the app flow plan.
### July 15th: Picture A Dose project began development.
### June 28th: Planning for Picture A Dose begins. 
