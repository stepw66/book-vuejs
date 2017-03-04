```
<div v-bind:class="{red: classRed}"></div>
<div v-bind:style="{background-color: red}"></div>
<div v-bind:style="{backgroundColor: red}"></div>
<div v-bind:style="multiple"></div>
```

```
new Vue({
    el: '#root',
    data: {
        classRed: false,
        red: "red"
    },
    computed: {
        backgroundColor: "red",
        borderWidth: "10px"
    }
})
```



