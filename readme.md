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
8. Add links to appropriate clothing offers based on the found weather condition. (Similar as an advertisement would do it).

### Hints for Task #8 (generated with ChatGPT)

To fetch products (image, URL, price) from a clothing store that match a given search query using JavaScript, you can use web scraping techniques along with the appropriate APIs (if available). Here is a sample code that can fetch the products from a store called "clothingstore.com":

```javascript
const request = require('request');
const cheerio = require('cheerio');

const searchQuery = 'red dress'; // Set the search query here
const url = `https://www.clothingstore.com/search?q=${searchQuery}`;

request(url, (error, response, body) => {
  if (!error && response.statusCode === 200) {
    const $ = cheerio.load(body);

    const products = [];
    $('.product-item').each((i, el) => {
      const product = {};
      product.image = $(el).find('.product-image img').attr('src');
      product.url = $(el).find('.product-title a').attr('href');
      product.price = $(el).find('.product-price').text().trim();
      products.push(product);
    });

    console.log(products);
  } else {
    console.log(error);
  }
});
```

In this code, we first set the search query and generate the URL based on it. We then use the `request` library to fetch the HTML of the search results page. Next, we use the `cheerio` library to parse the HTML and extract the relevant information for each product. Finally, we store the products in an array and log it to the console.

Note that this code is just an example, and you will need to customize it based on the specific structure and APIs of the clothing store you are targeting. Also, please make sure to respect the store's terms of service and robots.txt file when scraping their website.

