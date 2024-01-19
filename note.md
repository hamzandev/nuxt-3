
1. data -> proterpties (Nuxt 3 : we use ref() or basic variable)
2. method -> a list of function that we define for the spesific component
   In Nuxt 3 : we just create function to the root of `<script></script>` tag
3. computed -> computed properties
   Similar with basic properties, but this one can operate some logic with it's property
4. watch -> The watchers of propertiess
```
   watch(objToWatch, async (newValues, oldValues) => {
      Do anything with the objToWatch here...
   })
```