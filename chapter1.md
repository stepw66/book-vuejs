# การติดตั้ง Vue #

วิธีที่ง่ายที่สุดคือ include ผ่านแท็ก  

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



**จากตัวอย่างโค้ดด้านบน**

โครงสร้างโค้ดของวิว จะเริ่มจาก new instant Vue ขึ้นมา

```
new Vue({})
```

พารามิเตอร์ที่ส่งเข้าไป el: จะเป็นตัวบอกว่า เราจะแมป Vue ออปเจ็กตัวนี้เข้ากับอิลิเมนต์ HTML ตัวไหน ซึ่งเป็นสิ่งจำเป็น มันจะเป็นหน้าตาของออปเจ็กวิวตัวนี้ 

```
el: "#app"
```

data จะเป็น property ของออปเจ็ก Vue ที่เราสร้างขึ้นมา

```
data: 
      greeting: "Hello madam"     

```

ซึ่งเราสามารถแสดงข้อมูลที่อยู่ใน property ของออปเจ็ก Vue ด้วยวิธีง่ายคือ คร่อมชื่อ property ด้วยเครื่องหมาย {{ }}



```
<p>{{ greeting }}</p>
```
 

  
 
   