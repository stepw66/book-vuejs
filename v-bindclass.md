# Style object by class property

### เพิ่มชื่อคลาสเข้าไปใน div

สมมติว่าเราอยากจะเพิ่มคลาสให้ div โดยใช้ Vue เราจะทำได้อย่างนี้

```Vue
<style>
.redbox {display: block; width: 50px; height: 50px; background-color: red;}
</style>
<div id="app">
  <div v-bind:class="vueRedbox">This is redbox</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: 'redbox'
    }
  })
</script>
```

เรามีคลาสตัวหนึ่งชื่อว่า redbox

```
.redbox {display: block; width: 50px; height: 50px; background-color: red;}
```

เราให้ Vue ช่วยเพิ่มคลาส redbox นี้เข้าไปใน div ที่ต้องการโดยใช้คำสั่ง v-bind:class ช่วย ภายในเครื่องหมายคำพูด คือ ชื่อตัวแปรที่เราให้ Vue ช่วยแมปข้อมูลเข้ามายัง div

```
<div v-bind:class="vueRedbox">This is redbox</div>
```

ภายในตัวแปร vueRedbox เราให้เก็บค่า redbox ซึ่งก็คือชื่อคลาส css ที่เราสร้างไว้  หากจะกล่าวเป็นคำพูดเราก็จะกล่าวได้ว่า "ให้ Vue เอาค่าที่อยู่ในตัวแปร vueRedbox ไปใส่เป็นคลาสให้กับ div ตัวนี้" 

```
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: 'redbox'
    }
  })
</script>
```

เมื่อรันโค้ดนี้ ผลลัพธ์ที่ได้จะออกมาหน้าตาอย่างนี้ 

![](/assets/2017-03-05_19-20-28.jpg)

### เพิ่มคลาสเข้าไปใน div แบบใช้ object

Vue ยังมีอีกวิธีหนึ่งในการเพิ่มคลาสเข้าไปใน div หรือในอิลิเมนต์อื่นๆ ที่ต้องการคือส่งค่าเข้าไปแบบ object ดูตัวอย่าง

```Vue
<style>
#box{ border: 5px solid black; }  
.redbox { display: block; width: 50px; height: 50px; background-color: red; }
</style>
<div id="app">
  <div id="box" v-bind:class="{redbox: vueRedbox}">This is redbox</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: true
    }
  })
</script>
```

จะเห็นว่าเราส่ง {redbox: vueRedbox} เข้าไปให้ v-bind:class redbox นั่นเป็นชื่อ css คลาสที่เราต้องการใส่ให้อิลิเมนต์ ส่วน vueRedbox นั้นคือชื่อตัวแปรใน Vue ความหมายของประโยคนี้คือ ถ้าหากตัวแปร vueRedbox เป็น true ก็ให้เพิ่มคลาสชื่อ redbox เข้าไปให้ div แต่ถ้าหากตัวแปร vueRedbox มีค่าเป็น false ไม่ต้องเพิ่มคลาสชื่อ redbox เข้าไปให้ div หรือถ้าหาก div นั้นมีคลาสชื่อ redbox อยู่ก็ให้เอาออกซะ

```
<div id="box" v-bind:class="{redbox: vueRedbox}">This is redbox</div>
```

เมื่อรันโค้ดนี้จะให้ผลลัพธ์ดังนี้ 

![](/assets/2017-03-05_19-38-53.jpg)

แต่เมื่อเราลองเปลี่ยนตัวแปร vueRedbox ให้เป็น false



```
<style>
#box{ border: 5px solid black; }  
.redbox { display: block; width: 50px; height: 50px; background-color: red; }
</style>
<div id="app">
  <div id="box" v-bind:class="{redbox: vueRedbox}">This is redbox</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: false
    }
  })
</script>
```

ผลลัพธ์ที่ได้จะเป็นดังนี้ 

![](/assets/2017-03-05_19-40-41.jpg)

### เพิ่มคลาสเข้าไปใน div แบบใช้ object \(อีกแบบ\)

นอกจากการเพิ่ม css คลาสเข้าไปใน div โดยใช้ออบเจ็กตามวิธีด้านบน เรายังสามารถเขียนได้อีกวิธีหนึ่ง ดูตัวอย่าง

```
<style>
#box{ border: 5px solid black; }  
.redbox { display: block; width: 50px; height: 50px; background-color: red; }
</style>
<div id="app">
  <div id="box" v-bind:class="vueRedbox">This is redbox</div>
</div>

<script src="https://npmcdn.com/vue/dist/vue.js"></script>
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: {redbox: true}
    }
  })
</script>
```

เราบอกว่าให้เอาค่าที่อยู่ในตัวแปร vueRedbox แมปเข้าไปในพร้อพเพอตี้ class ของ div

```
<div id="box" v-bind:class="vueRedbox">This is redbox</div>
```

ส่วนตัวแปร vueRedbox ใน Vue มันเก็บออเจ็กจาวาสคริปต์ไว้ redbox หากมีค่าเป็น true ผลลัพธ์ที่ออกมากล่องก็จะเป็นสีแดง แต่ถ้าหาก redbox เป็น false กล่องก็จะไม่เป็นสีแดง

```
<script>
  new Vue({
    el: '#app',
    data: {
      vueRedbox: {redbox: true}
    }
  })
</script>
```

ผลลัพธ์

![](/assets/2017-03-05_19-38-53.jpg)

### การเพิ่มคลาสหลายตัวเข้าไปใน div





xxx





