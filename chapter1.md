# การติดตั้ง Vue

วิธีที่ง่ายที่สุดคือ include ผ่านแท็ก &lt;script&gt;

ชี้ไปที่ cdn ของ npmcdn.com ก็ได้เขาปล่อยไฟล์ให้เราเรียกใช้งาน

```
<script src="https://npmcdn.com/vue/dist/vue.js"></script>
```

หรือจะดาวน์โหลด Vue มาเก็บไว้ในเครื่อง ก็ได้ ซึ่งคุณสามารถดาวน์โหลดได้ที่ URL นี้   [https://unpkg.com/vue](https://unpkg.com/vue)

```
<script src="Your path to js file."></script>
```

**ตัวอย่างโค้ด**

```
<div id="app">
  <p>{{ greeting }}</p>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    data: {
      greeting: "Hello madam"
    } 
  })
</script>
```



มันยังมีวิธีติดตั้งผ่าน node, npm และอีกหลายวิธี แต่ผมไม่ขอกล่าวเพราะมันจะดูยุ่งยาก หากท่านสนใจ สามารถค้นหาในกูเกิลด้วยคำ "how to install vuejs by node" , "how to install vuejs by npm"



