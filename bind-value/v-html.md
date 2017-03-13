# v-html

จากตัวอย่างวิธีการนำข้อมูลในตัวแปรไปแสดง ตามข้างล่าง



```js
<div id="app">
    <p>{{ greeting }}< /p>
</div>

<script src="https:/pmcdn.com/vue/dist/vue.js"></script>
<script >
new Vue({ 
    el: "#app", 
    data: { greeting: "Hello World" } 
})
</script>
```



เราเอาค่าจากตัวแปร greeting ไปแสดงที่แท็ก p  การแสดงข้อมูลโดยใช้รูปแบบนี้ จะแสดงข้อมูลที่ไม่ได้เป็น html เท่านั้น เพราะว่า Vue จะทำการแปลงโค้ด html ให้เป็นข้อความธรรมดา ลองดูตัวอย่าง

## ตัวอย่าง

```
<div id="app">
  <div>{{ greeting }}</div>
</div>

<script src="js/vue.js"></script>
<script >
new Vue({
  el: "#app",
  data: { 
    greeting: "<h1>How to use v-html</h1>"
  }
})
</script>
```

## ผลลัพธ์

![](/assets/2017-03-13_8-48-14.jpg)

แน่นอนว่า Vue ทำอย่างนี้ก็เพื่อความปลอดภัย เพราะบางที่บางแห่งเราไม่ได้ต้องการให้ยูสเซอร์ป้อน html เข้ามาแล้วแสดงเป็นอะไรก็ได้ 

ทีนี้ถ้าหากเราต้องการแสดง html จริงๆ จะทำไง 

Vue เตรียมคำสั่งไว้ให้คำสั่งหนึ่ง คือ v-html ลองดูตัวอย่าง

## ตัวอย่าง

```
<div id="app">
  <div v-html="greeting"></div>
</div>

<script src="js/vue.js"></script>
<script >
new Vue({
  el: "#app",
  data: { 
    greeting: "<h1>How to use v-html</h1>"
  }
})
</script>
```

## ผลลัพธ์

![](/assets/2017-03-13_8-55-39.jpg)



## คำอธิบาย

เราแค่เปลี่ยนคำสั่งการแสดงจาก 

```
<div>{{ greeting }}</div>
```

ไปเป็น 

```
<div v-html="greeting"></div>
```















