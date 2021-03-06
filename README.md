# Unit 06 Server-Side APIs Homework: Weather Dashboard
A weather dashboard which displays current weather and forecast for a searched city. Users can search for a city, and if found the app will return the current weather, as well as a forecast of the next 5 days. The user's search history is saved as a button for them to quickly check the weather of that city again.

## Approach
I started by dividing the main task into smaller tasks, as outlined below:
1. Get the user input city
2. Send the request to the Openweather server and retrieve the current weather and forecast
3. Show the information on screen
4. Create a button that does the same thing as steps 2 and 3 for the weather in that city again

In this approach I started with a functionality focus first, then I worked on the styling. Or well, that's what I'd like to say but I ended up developing the HTML/CSS skeleton first anyway. I decided to try matching the styling in the example image to block out the necessary fields for the JavaScript.

## Challenges
The major challenge in this assignment was getting the 5 day forecast properly using the Openweather API. The 5 day weather call returns the forecast in intervals of three hours, up to 5 days past the current date. This means the array has more data to iterate through than needed. To pick out just one value from each day I used a condition to check for the forecast at a certain time (noon) each day, writing only that data to HTML.

Getting the UV index of the searched city was an issue, because unlike the search for the current weather and the forecast the UV API only accepted longitude and latitude coordinates. To remedy this problem, I called my UV index function from within the current weather function's Ajax call, since the response returned the city's longitude and latitude.

I wanted to have the search history buttons only appear if the city existed. I found that by simply calling the function inside an AJAX call, it would only run if the request was successful. I could also use the name on the server to make sure the button name is capitalized, therefore allowing the conditional that checks if the button exists to work properly.