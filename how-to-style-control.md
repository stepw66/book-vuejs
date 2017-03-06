# Style element by style property

เวลาเราเขียน style ใส่เข้าไปใน html ธรรมดาๆ หน้าตามันจะประมาณนี้

```
<div style="background-coloc:red; border:1px solid black;"></div>
```

เราใช้ Vue ช่วยแทรก style แบบนี้ได้ในหลายๆรูปแบบ เรามาไล่ดูกันว่า Vue จะช่วยเราได้อย่างไร

### แบบธรรมดาที่สุด

เราใช้คำสั่ง v-bind:style เป็นตัวช่วยผูก style เข้าไปใน div ดูตัวอย่าง

```
<div id="app">
  <div v-bind:style="{backgroundColor: 'red'}">This is box</div>
  <div v-bind:style="{'background-color': 'yellow'}">This is box</div>
  <div v-bind:style="{'border': '1px solid black'}">This is box</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {} 
  })
</script>
```

Vue นั้นจะไม่สร้างคำสั่ง style ขึ้นมาใหม่ มันจะหยิบเอามาจาก css โดยตรง เพราะฉะนั้น เราเคยใช้ชื่อ style อย่างไรก็ใช้อย่างนั้น

จากโค้ดจะเห็นว่าเราเขียน style ได้ 2 รูปแบบ คือแบบ css style กับ camel case style แต่ถึงจะเป็น camel case style มันก็หยิบยืมชื่อ style มาจาก css อยู่ดี แค่ตัดเครื่องหมายขีดกลางออก แล้วเปลี่ยนอักษรตัวแรกของคำหลังเป็นตัวอักษรตัวใหญ่ เท่านั้น

ข้อสังเกตุอย่างหนึ่งก็คือ หากเราเลือกใช้ camel case ไม่ต้องคร่อมค่าด้วยเครื่องหมายคำพูด แต่ถ้าหากเราเลือกใช้ตามชื่อ css เป๊ะๆ เราต้องคร่อมค่าด้วยเครื่องหมายคำพูด

```
<div v-bind:style="{backgroundColor: 'red'}">This is box</div>
<div v-bind:style="{'background-color': 'yellow'}">This is box</div>
<div v-bind:style="{'border': '1px solid black'}">This is box</div>
```

**ผลลัพธ์**

### ![](/assets/2017-03-06_10-21-15.jpg)

### แมป Style อย่างง่ายอีกวิธีหนึ่ง

นอกจากเราจะระบุค่า css สไตล์ลงไปตรงๆ ดังตัวอย่างด้านบน เรายังสามารถใช้ตัวแปรของ Vue เข้ามาช่วยได้ด้วย

```
<div id="app">
  <div v-bind:style="{backgroundColor: vueRed}">This is box</div>
  <div v-bind:style="{'background-color': vueYellow}">This is box</div>
  <div v-bind:style="{'border': vueBorder}">This is box</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {
      vueRed: 'red',
      vueYellow: 'yellow',
      vueBorder: '1px solid black' 
    } 
  })
</script>
```

vueRed, vueYellow, vueBorder คือชื่อตัวแปร Vue

```
<div v-bind:style="{backgroundColor: vueRed}">This is box</div>
<div v-bind:style="{'background-color': vueYellow}">This is box</div>
<div v-bind:style="{'border': vueBorder}">This is box</div>
```

ในตัวแปรต่างๆ เก็บค่าที่ต้องการไว้

```
<script>
  new Vue({
    el: '#app',
    data: {
      vueRed: 'red',
      vueYellow: 'yellow',
      vueBorder: '1px solid black' 
    } 
  })
</script>
```

**ผลลัพธ์ที่ได้**

![](/assets/2017-03-06_10-21-15.jpg)

### แมป Style หลายค่า

ในกรณีที่เราต้องการจะแมป css สไตล์หลายๆค่า เราสามารถทำได้ดังนี้

```
<div id="app">
  <div v-bind:style="{'background-color': 'red', 'border': '2px solid black'}">This is box</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {} 
  })
</script>
```

เราส่งค่าหลายค่าให้ v-bind:style ได้เลย

```
<div v-bind:style="{'background-color': 'red', 'border': '2px solid black'}">This is box</div>
```

### แมป Style ด้วยอะเรย์

อีกวิธีในการแมปค่า css สไตล์คือส่งค่าไปให้ v-bind:style แบบอะเรย์ ดูตัวอย่าง

```
<div id="app">
  <div v-bind:style="[{'border': '2px solid black'},{'background-color': 'red'}]">This is box</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {} 
  })
</script>
```



