# การติดตั้งVue

วิธีที่ง่ายที่สุดคือincludeผ่านแท็ก&lt;script&gt;

ชี้ไปที่cdnของnpmcdn.comก็ได้เขาปล่อยไฟล์ให้เราเรียกใช้งาน

```
<script src="https:/pmcdn.com/vue/dist/vue.js"></script>
```

หรือจะดาวน์โหลด Vue มาเก็บไว้ในเครื่อง ก็ได้ ซึ่งคุณสามารถดาวน์โหลดได้ที่ URL นี้ [https://unpkg.com/vue](https://unpkg.com/vue)

```
<script src="Your path to js file."></script>
```

**ตัวอย่างโค้ด**

```js
<div id="app">
    <p>{{ greeting }}< /p>
</div>
<script src="https:/pmcdn.com/vue/dist/vue.js"></script>
<script>
new Vue({ el: "#app", data: { greeting: "Hello madam" } })
</script>
```

มันยังมีวิธีติดตั้งผ่านnode,npmและอีกหลายวิธีแต่ผมไม่ขอกล่าวเพราะมันจะดูยุ่งยากหากท่านสนใจสามารถค้นหาในกูเกิลด้วยคำ"howtoinstallvuejsbynode","howtoinstallvuejsbynpm"

**จากตัวอย่างโค้ดด้านบน**

โครงสร้างโค้ดของวิวจะเริ่มจาก new instant Vue ขึ้นมา

```
new Vue({})
```

พารามิเตอร์ที่ส่งเข้าไป el: จะเป็นตัวบอกว่าเราจะแมป Vue ออปเจ็กตัวนี้เข้ากับอิลิเมนต์ HTML ตัวไหนซึ่งเป็นสิ่งจำเป็นมันจะเป็นหน้าตาของออปเจ็กวิวตัวนี้

```
el: "#app"
```

dataจะเป็นpropertyของออปเจ็กVueที่เราสร้างขึ้นมา

```
data: {
            greeting: "Hello madam"
      } 
```

ซึ่งเราสามารถแสดงข้อมูลที่อยู่ใน property ของออปเจ็ก Vue ด้วยวิธีง่ายคือคร่อมชื่อ property ด้วยเครื่องหมาย

```
<p>
{{ greeting }}
</p>
```



