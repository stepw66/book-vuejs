# v-bind

[ตอนก่อน](/how/start-using-vue.md)เราได้ดูวิธีนำข้อมูลจาก Vue ไปแสดงแล้ว ทีนี้ถ้าหากเราต้องการเอาข้อมูลไปผูกกับ attribute อื่นๆของ HTML เราทำยังไง Vue มีคำสั่ง v-bind ไว้สำหรับผูกค่าที่ต้องการเข้ากับ attribute  HTML

## ตัวอย่าง

```
<style>
  .active{ background-color: red}
</style>

<div id="app">
  <p v-bind:class="gClass">{{ greeting }}</p>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    data: {
      greeting: "Hello World",
      gClass: 'active'
    } 
  })
</script>
```

## ผลลัพธ์

จะเห็นว่าแท็ก p ของเรามีคลาส active ทำให้พื้นหลังแดง

![](/assets/2017-03-10_14-01-00.jpg)

## อธิบาย

สร้างตัวแปรเก็บชื่อ class ในที่นี้ตั้งชื่อว่า gClass เก็บ active ไว้ภายใน

```
data: {
      greeting: "Hello World",
      gClass: 'active'
} 
```

จากนั้น bind ชื่อตัวแปรเข้ากับแอททริบิวต์ class

```
<p v-bind:class="gClass">{{ greeting }}</p>
```

เมื่อรันโค้ด Vue จะเอาคำว่า active ไปใส่ให้ในแอททริบิวต์ class ของแท็ก p ให้

## v-bind แบบ javascript object

นอกจากเราจะเก็บค่าสตริงไว้ในตัวแปรเพื่อนำไปใช้กับ v-bind แล้ว เรายังสามารถเก็บค่าในรูปแบบ javascript object ได้ด้วย

## ตัวอย่าง

```
<style>
  .active{ background-color: red}
</style>

<div id="app">
  <p v-bind:class="gClass">{{ greeting }}</p>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    data: {
      greeting: "Hello World",
      gClass: {active: true}
    } 
  })
</script>
```

## ผลลัพธ์

![](/assets/2017-03-10_14-30-17.jpg)

## อธิบาย

ตัวแปร gClass ของเรา เรากำหนดให้เก็บค่าแบบ javascript object สังเกตุให้ดีนะครับ คำว่า active เราใช้เป็นคีย์ ถ้าหากเลื่อนไปดูการกำหนดค่าในแบบแรก คำว่า active เราเป็น string  ค่าของ active เรากำหนดเป็น true/false

ถ้าค่า active เท่ากับ true , Vue จะเอาคำว่า active ไปใส่ให้ในแอททริบิวต์ class ของแท็ก p

ถ้าค่า active เท่ากับ false, Vue จะเอาคำว่า active ออกจากแอททริบิวต์ class ของแท็ก p

```
<script>
  new Vue({
    el: "#app",
    data: {
      greeting: "Hello World",
      gClass: {active: true}
    } 
  })
</script>
```

## ตัวอย่างเพิ่มเติม

```
<style>
  .active{ background-color: red}
</style>

<div id="app">
  <input type="checkbox" v-bind:checked="isChecked"> Cow
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: "#app",
    data: {
      isChecked: true
    } 
  })
</script>
```

## ผลลัพธ์

![](/assets/2017-03-10_16-54-15.jpg)



