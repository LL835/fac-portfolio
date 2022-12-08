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
form.addEventListener("submit", (e) => {
    e.preventDefault();
    const input = document.querySelector("input");
    const searchTerm = input.value.toLowerCase().trim(); 
    input.value = "";
    removeBox();
    createOutput();
    getGif(searchTerm);
    getDefinition(searchTerm);
})   
```
## 3. Use promises to access values that aren’t available synchronously
See #1.
## 4. Use the fetch method to make HTTP requests and receive responses
See #1.
## 5. Configure the options argument of the fetch method to make GET and POST requests

Didn't use this in the project but practised it in the workshop

```js
const data = { name: "oli" };

fetch("https://echo.oliverjam.workers.dev/json", {
  method: "POST",
  body: JSON.stringify(data),
  headers: { "content-type": "application/json" },
})
  .then((response) => {
    if (!response.ok) throw new Error(response.status);
    return response.json();
  })
  .then((json) => console.log(json))
  .catch((error) => console.error(error));
```

## 6. Use the map array method to create a new array containing new values

We didn't use map in our project but I've used it for Execute Program.

```js
[1, 2, 3].map(num => num * 10);
```

## 7. Use the filter array method to create a new array with certain values removed

We didn't use filter in our project but I've used it for Execute Program.

```js
const arrays = [
  [1, 2],
  [2, 3],
  [3, 4],
];
arrays.filter(array => array.includes(2));
```

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

```js
tile.classList.toggle("revealed");
```

## 11. Use consistent layout and spacing

I used modifier classes in the first workshop:

```html
    <main class="center width-lg stack-xl">
```
## 12. Follow a spacing guideline to give our app a consistent feel

```css
.center {
  max-width: 40rem;
  margin-left: auto;
  margin-right: auto;
}

.width-sm {
  max-width: 20rem;
}

.width-lg {
  max-width: 60rem;
}

.stack-sm > * + * {
  margin-top: 0.5rem;
}

.stack-md > * + * {
  margin-top: 1rem;
}

.stack-lg > * + * {
  margin-top: 2rem;
}

```
## 13. Debug client side JS in our web browser

## 14. Use console.log() to help us debug our code

This has been deleted in the final version but I used console.log to check what the returned promised object look like so that I could access the different gif URls.

```js
.then(x => {
console.log(x)}

```

