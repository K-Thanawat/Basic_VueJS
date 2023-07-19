<template>
    <section>
      <img :src="image" alt="" :width="320" ref="imageURL">
      <!-- <p>ป้อนชื่อเล่น : <input type="text" v-on:input="setNickName"></p> -->
      <h1>ชื่อผู้สมัครงาน {{getFullName}}</h1>
      {{ isVisible }} <br>
      <button @click="toggleVisible">{{ isVisible ? "ซ่อน" : "แสดง" }} แสดงรายละเอียด</button>
      <!-- <form @submit.prevent="submitForm">
        <label>ป้อนชื่อเล่น :</label>
         v-on:input="setNickName" 
        <input type="text" ref="nickNameEL">
        <button type="submit">บันทึก</button>
      </form> -->
      <button @click="showRef">แสดง Ref</button>
      <h2>ชื่อเล่น : {{ nickName }}</h2>
      <h2>อายุ : {{ age }}</h2>
      <h3>เงินเดือน : {{ salary }}</h3>
      <h3>รายได้ต่อปี : {{ getIncome }}</h3>
      <h3>ตำแหน่งงาน : {{ getDepartment }}</h3>
      <button @click="addSalary(5000)">เพิ่มเงินเดือน</button>
      <button @click="delSalary(5000)">ลดเงินเดือน</button>
      <h3>Method : {{ getRandomByMethod() }}</h3>
      <hr>
      <h3>Computed : {{ getRandomByComputed }}</h3>
      <article v-show="isVisible">
        <p>ที่อยู่ : <span v-html="address"></span></p>
        <p>Social : <a :href="social" target="_blank">Google</a></p>
        <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
        <div v-else>
          <p>งานอดิเรก :</p>
          <ul>
            <li v-for="(item,index) in hobby" :key="index">{{ item }}</li>
          </ul>
        </div>
        <p v-if="hobby.length === 0">ไม่มีข้อมูลพื้นฐาน</p>
        <p>ข้อมูลพื้นฐาน :</p>
        <ul>
          <li li v-for="(item,key) in general" :key="key">{{ key }} - {{ item }}</li>
        </ul>
      </article>
      <!-- <button @click="showData">คลิ๊กแสดงข้อมูล</button>
      <button @click="increment(10)">คลิ๊กเพิ่ม</button>
      <button @click="decrement">คลิ๊กลบ</button> -->
    </section>
  </template>
  
  <script>
  
  export default {
    name: 'App',
    data(){
      return{
        firstName:"Thanawat",
        lastName:"K",
        // nickName:"",
        age:25,
        address:"<i>เชียงใหม่</i>",
        image:"https://optimise2.assets-servd.host/maniacal-finch/production/animals/african-lion-01-01.jpg?w=1200&auto=compress%2Cformat&fit=crop&dm=1658933674&s=4b63f926a0f524f2087a8e0613282bdb",
        social:"http://www.google.com",
        hobby:[
          "ดูหนัง" , "ฟังเพลง" , "เล่นเกมส์" , "ทำสวน"
        ],
        general:{
          gender:"ชาย" , weight:70 , height:170 , status:false
        },
        isVisible:false ,
        salary: 40000,
      }
    },
    methods:{
      // showData(){
      //   alert(this.getFullName())
      // },
      // increment(value){
      //   this.age+=value
      // },
      // decrement(){
      //   this.age--
      // },
      // // setNickName(event){
      // //   this.nickName = event.target.value;
      // // },
      // submitForm(){
      //   this.nickName=this.$refs.nickNameEL.value
      // },
      // showRef(){
      //   console.log(this.$refs.imageURL)
      //   console.log(this.$refs.nickNameEL)
      // }
      toggleVisible(){
        this.isVisible = !this.isVisible
      },
      getRandomByMethod(){
        return Math.random()
      },
      addSalary(value){
        this.salary += value
      },
      delSalary(value){
        this.salary -= value
      }
    },
    computed:{
      getFullName(){
        return `${this.firstName} ${this.lastName}`
      },
      getRandomByComputed(){
        return Math.random()
      },
      getIncome(){
        return this.salary * 12;
      },
      getDepartment(){
        return this.salary >= 35000 ? "Project Manager" : "Programmer"
      }
    },
    watch:{
      salary(value){
        if(value > 50000){
          alert("เงินเดือนไม่ควรเกิน 50000 บาท")
          setTimeout(() =>{
            this.salary = 50000
          }, 2000)
        }
      }
    }
  }
  </script>
  
  <style>
  /* #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  } */
  </style>
  