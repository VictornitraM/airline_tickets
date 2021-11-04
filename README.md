# VUEJS Assessments - Live UI Updates & Data Table

You can find the 2nd project (inventory_management) in a subfolder of this git repository.

## Project setup (to get the folder node_modules)
```
npm install
```

### Compiles and hot-reloads for development (defaults to localhost:8080)
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


### Answers to Theory #4
```
1. The Virtual DOM is representing the actual DOM; It's a layer between the actual DOM 
and the Vue Instance. Compared to the actual DOM, it loads very fast. The virtual DOM 
looks for changes and only updates the associated nodes, not the entire DOM, 
through which shorter loading times are guaranteed.

2. A slot allows you to add content in your template via the component. 
If you have a <slot></slot> in your template, you can add Text, HTML 
or even other components to be rendered in the current component. 
Scoped slots work the same, but they also allow a parent to look at it's child data.

3. Most memory leaks in Vue.js are caused 
by other libraries used in your application. 
Common memory leaks happen when you don't properly 
clean up components and something stays left behind in the DOM. 
To resolve such issues, you can use e.g. the beforeDestroy() method 
from VueJS to destroy/unmount any components that Vue left in the DOM.

4. push(), splice(), reverse(), sort(), pop(), shift(), unshift()   

5. Generally speaking, the components options will take priority when merging with a mixin. 
E.g. exception: hook functions (Mixin hooks will be called before the component's hooks)
You can customise those strategies to define how a mixin and a component should merge, in case of conflict.
```