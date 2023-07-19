<template>
  <!-- <h1>{{ message }}</h1> -->
  <!-- <Person name="A" salary=30000 />
        <Person name="B" salary=35000 />
  <Person name="C" salary=25000 />-->
  <ul>
    <Person
      v-for="(item , index) in employees"
      :key="index"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :gender="item.gender"
      :skill="item.skill"
    />
  </ul>
    <!-- :isVisible="item.isVisible"
    @show="toggleVisible"
    @delete="removeEmployee"
    :id="item.id" -->
</template>
  
<script>
import Person from "./Person.vue";
export default {
  name: "ListData",
  components: {
    Person,
  },
  props:["employees"]
  // data(){
  //     return{
  //         message:"แสดงรายชื่อพนักงานทุกคน"
  //     }
  // }
//   data() {
//     return {
//       employees: [
//         {id:1 , name: "A", salary: 15000 , department:"โปรแกรมเมอร์" , isVisible:false},
//         {id:2 , name: "B", salary: 25000 , department:"การตลาด" , isVisible:false},
//         {id:3 , name: "C", salary: 35000 , department:"หัวหน้าโปรแกรมเมอร์" , isVisible:false},
//         {id:4 , name: "D", salary: 25000 , department:"บุคคล" , isVisible:false},
//         {id:5 , name: "E", salary: 15000 , department:"โปรแกรมเมอร์" , isVisible:false},
//       ],
//     };
//   },
//   methods:{
//     toggleVisible(id){
//         this.employees = this.employees.map((item) => {
//             if(item.id === id){
//                 return {...item , isVisible:!item.isVisible}
//             }
//             return item
//         })
//     },
//     removeEmployee(id){
//         this.employees = this.employees.filter(item => {
//             return item.id !== id
//         })
//     }
//   }
};
</script>

<style scoped>
ul{
    list-style: none;
    margin: 1rem 0;
    padding: 0;
}
</style>