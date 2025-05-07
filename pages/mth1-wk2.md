---
layout: center
transition: fade-out
---

# [Month 1 Week 2]{.gradient-text}

<!-- CSS styling for .gradient-text class -->
<style>
    .gradient-text {
      background: linear-gradient(45deg, #4EC5D4 10%, #008080 20%);
      -webkit-background-clip: text;
      -moz-background-clip: text;
      -webkit-text-fill-color: transparent;
      -moz-text-fill-color: transparent;
      font-size: 2em; 
    }
   
</style>

---

## [🤝 Promises]{.text-teal-400}

<br>

A promise is an object that represents a future result of an asynchronous operation. It has 3 states. They are :
<v-clicks>

1. Pending - initial state
2. Fulfilled - successful completion
3. Rejected - Operation Failed

</v-clicks>

<br>

### How to create a promise?

Simply:

```js
newPromise();
```

<br>

**A promise will take the function for the fulfilled and the rejected :**

```js
newPromise(resolve, reject);
```

<br>



---

Sample syntax:

```js 
const myPromise = newPromise ((resolve, reject) => {
If () {
resolve(value); // promise is fulfilled with value
} else {
reject(error); // promise is rejected with error
}
});
```

<br>

---

Sample Code:

```js {all|1-2|4-6|7-11|14-18|19-21|all}
function fetchData(url) {
  return new Promise((resolve, reject) => {
    // Simulating network request
    setTimeout(() => {
      if (url.includes("success")) {
        resolve({ data: "Here is your data", status: 200 });
      } else {
        reject({ error: "Failed to fetch data", status: 404 });
      }
    }, 2000);
  });
}

// Using the promise
fetchData("https://api.example.com/success")
  .then((response) => {
    console.log("Success:", response.data);
  })
  .catch((error) => {
    console.log("Error:", error.error);
  });
```

---

## [⏱️Async / Await]{.text-teal-400}

It is a Modern way to write Promises

**Note** : Putting 'async' in front of a function automatically makes it a **Promise**.

```js
async function getData() {
  try {
    const response = await fetchData("https://api.example.com/success");
    console.log("Data:", response.data);
    return response;
  } catch (error) {
    console.error("Error:", error);
    throw error;
  }
}

// Call the async function
getData().then((data) => {
  console.log("Processing data further");
});
```
