# Weather app
This app shows the temperature at any given location. The user enters the location
## Source
The source code is copied from [this page](https://www.codewithrandom.com/2022/10/12/weather-app-using-javascript/) but then changed to use other APIs that do not need an authentication key.

## Bug reports
### Bug #01 Initial date is wrong
The date on the page when I load it is not the current date.
#### How to reproduce
Open the page and look at the day and date below the initial city. It is always Monday the 30th of May. I want it to be the current date.

### Bug #02 Temperature too inprecise
The temperature is displayed as integer. It should only be rounded only to half degrees (.0 or .5).
#### How to reproduce
Open the page and search for a city. If the city is found and the weather is shown, the temperature is shown as integer number.


## Tasks
1. Fix all bugs.
2. Use a local background image.
3. Add a button to refresh the weather at the current location.
4. Replace the word describing the weather condition by an appropriate icon (use some emoticons from https://unicode.org/emoji/charts/full-emoji-list.html#sky_&_weather).
5. Add the possibility to save locations to a list.
6. Allow to select a location from the list and show the weather there.
7. Allow to delete a location from the list.