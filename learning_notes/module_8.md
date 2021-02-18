# Module 8 (Web Storage)

On this part of module, the course teaches about Web Storage. Here is my learning notes:

1. Learned some new general knowledge of web storage:
- Web storage is categorized based on domain so that only the respected domain can access its web storage.
- Each domain has 10MB of data in web storage.

2. Learned about **Web Storage types**. There are 2 types: `sessionStorage` and `localStorage`. Before using any of them, we need to check whether the browser support web storage. Web storage is stored in `key-value` pair and can store primitive value like number, boolean, and string. For more, look [here](https://www.dicoding.com/academies/123/tutorials/5890?from=5888). All the code here is taken from there.
```
To check web storage availability
=================================
if (typeof(Storage) !== "undefined") {
    // Browser supports sessionStorage/localStorage.
} else {
    // Browser doesn't support sessionStorage/LocalStorage
}
```
## Session Storage
Used to store temporary data on browser that will be gone when the tab/browser is closed. To access sessionStorage, we can use `sessionStorage` object with `getItem()` and `setItem()`.
```
<script>
       const cacheKey = "NUMBER";
       if (typeof(Storage) !== "undefined") {
           if (sessionStorage.getItem(cacheKey) === "undefined") {
               sessionStorage.setItem(cacheKey, 0);
           }
 
           const button = document.querySelector("#button");
           const count = document.querySelector("#count");
           button.addEventListener('click', function(event) {
               let number = sessionStorage.getItem(cacheKey);
               number++;
               sessionStorage.setItem(cacheKey, number);
               count.innerText = sessionStorage.getItem(cacheKey);
           })
       } else {
           alert("Browser doesn't support Web Storage")
       }
   </script>
```

## Local Storage
Used to store temporary data on browser that will **NOT** be gone when the tab/browser is closed. To access localStorage, we can use `localStorage` object with `getItem()` and `setItem()`.
```
The example is same as sessionStorage, but change sessionStorage to localStorage.
```

3. 