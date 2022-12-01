# HTTP
## 1. Write code that executes asynchronously
```js
  fetch(`https://api.giphy.com/v1/gifs/search?api_key=${apiKey}&q=${word}&limit=50&offset=0&rating=g&lang=en`)
      .then(response => {
          if (!response.ok){
              throw new Error(response.status); // throw error if GIPHY doesn't respond
          }
          return response.json()
      })
```
## 2. Use callbacks to access values that aren’t available synchronously
```js
  .then(randomGif => {
      const randomGifURL = randomGif.data.images.downsized.url; //finds the link of the gif
      const randomGifAltText = randomGif.data.title;//finds the title of the gif to be used as the alt text
      gif.src = randomGifURL; //sets link of gif to returned data
      gif.alt = randomGifAltText; //sets alt text to returned data
  })            
```
## 3. Use promises to access values that aren’t available synchronously
See #1.
## 4. Use the fetch method to make HTTP requests and receive responses
See #1.
## 5. Configure the options argument of the fetch method to make GET and POST requests
## 6. Use the map array method to create a new array containing new values
## 7. Use the filter array method to create a new array with certain values removed
## 8. Access DOM nodes using a variety of selectors
```js
const form = document.querySelector("form");
const headingOutput = document.querySelector(".search-results-heading");
```
## 9. Add and remove DOM nodes to change the content on the page
```js
document.querySelector(".hero").remove();
```

## 10. Toggle the classes applied to DOM nodes to change their CSS properties
## 11. Use consistent layout and spacing
## 12. Follow a spacing guideline to give our app a consistent feel
## 13. Debug client side JS in our web browser
## 14. Use console.log() to help us debug our code


