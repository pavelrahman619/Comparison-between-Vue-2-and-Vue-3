# Comparison between Vue 2 and Vue 3

## Vue Instance

### Vue 2

```
var app = new Vue({
  el: '#app',
  data: {
    product: 'Socks',
    description: 'A pair of warm fuzzy socks'
  } 
}) 
```

### Vue 3
```
const app = Vue.createApp({
    data() {
        return {
            product: 'Socks',
            description: 'A warm fuzzy pair of socks.' 
        }
    }
})
```

## Attribute Binding

### Vue 2 and Vue 3 

HTML
```
<div class="product-info">
<h1>{{ product }}</h1>
<!-- solution -->
<a :href="url">Made by Vue Mastery</a>
<!-- solution -->
</div>
```

JS
```
const app = Vue.createApp({
    data() {
        return {
            product: 'Socks',
            image: './assets/images/socks_green.jpg',
            // solution
            url: 'https://www.vuemastery.com/'
            // solution
        }
    }
})
```

## Global Configurations
Vue 3 provides different global configurations but it makes it difficult to share a copy of configuration to multiple apps

### Vue 2
```
// this mixin affects both below instances
Vue.mixin({ /* ... */ })

const app1 = new Vue({ el: '#app-1' })
const app2 = new Vue({ el: '#app-2' })
```

### Vue 3
```
const app = createApp(App)
// This configuration effect only 1 instance
app.mixin(/* ... */)
app.mount('#app')
```

## Multiple Roots
In Vue 2, you implement only one single root node in the template but Vue 3 no longer requires a single root node for components that means it provides developer multiple root in the template.

### Vue 2
```
<template>
  <div>
    <h1>{{ msg }}</h1>
    <button @click="count++">count is: {{ count }}</button>
    <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
  </div>
</template>
```

### Vue 3
```
<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
</template>
```

