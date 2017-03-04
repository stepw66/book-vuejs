



.

```
<div id="root">
    <p v-bind:class="classes">multiple class</p>
</div>
```

.

```
new Vue({
    el: '#root',
    data: {
        classes: ''
    },
    compute: {
        classes: function(){
            return {
                firstclass: true,
                secodeclass: true
            }
        }
    }
})
```



