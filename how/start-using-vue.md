# เริ่มต้นใช้งาน Vue

เราจะเริ่มต้นโค้ดกันด้วยธรรมเนียมของโปรแกรมเมอร์ นั่นคือ Hello World  จงดู่โค้ด

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

## ผลลัพธ์

![](/assets/2017-03-10_11-30-24.jpg)

## คำอธิบาย

ก่อนอื่นเราต้อง include  vue เข้ามาก่อน แต่เหตุที่เอาไปไว้ด้านล่าง HTML เพราะว่าอยากให้หน้าเว็บดาวน์โหลด HTML ให้เสร็จก่อน จึงมาดาวน์โหลด javascript

```
<script src="https:/pmcdn.com/vue/dist/vue.js"></script>
```

จากนั้นเราจะสร้างออบเจ็ก Vue ขึ้นมา ออบเจ็กตัวนี้จะเป็นตัวเก็บดาต้า ฟังก์ชั่น และลอจิกการทำงานต่างๆ  เราจะเจอการสร้างออบเจ็กแบบนี้ตลอดเวลาที่ใช้งาน Vue เพราะฉะนั้นถ้าตอนนี้ยังงงๆก็ไม่ต้องกังวล

```
new Vue({})
```

el คือตัวบอกว่าส่วนการแสดงผลของออเจ็กที่สร้างขึ้นนี้คือตัวไหน ค่าข้างในจะใช้รูปแบบการอ้างอิงแบบ css

```
el: "#app"
```

data เป็นตัวเก็บตัวแปร ถ้าจะเรียกแบบออบเจ็กก็ต้องพูดว่า data เป็นตัวเก็บพร้อพเพอตี้

```
data: { greeting: "Hello World" }
```

หลังจากเรามีข้อมูลแล้วต่อจากนั้นเราก็เอาข้อมูลนั้นไปแสดงผล โดยผูกตัวแปรเข้ากับวิว

```
<p>{{ greeting }}< /p>
```



ข้อจะต้องจำไว้อย่างหนึ่งก็คือ เราจะเอาตัวแปรใน Vue ไปใช้นอก scope ที่กำหนดไว้ใน el ไม่ได้

## ตัวอย่าง

```

<div id="main">
  <div id="app">
    <p>{{ greeting }}</p>
  </div>
  <div id="footer">
    <p>{{ greeting }}</p>
  </div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    data: {
      greeting: "Hello World" 
    } 
  })
</script>
```

## ผลลัพธ์

![](/assets/2017-03-10_11-35-28.jpg)



