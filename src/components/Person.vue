<template>
  <card-s>
    <template v-slot:card-header>
      <h1>ชื่อ : {{ name }}</h1>
    </template>

    <!-- <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>-->

    <template v-slot:card-content>
      <p>เพศ : {{ gender }}</p>
      <p>เงินเดือน : {{ salary }} บาท</p>
      <p>ตำแหน่งงาน : {{ department }}</p>
      <p>ทักษะด้านภาษา : {{ skill }}</p>
      <!-- <transition name="fade">
        <div v-show="isVisible">
          
        </div>
      </transition>-->
    </template>
  </card-s>
</template>
  
<script>
import CardS from "./CardS.vue";
export default {
  name: "PersonS",
  components: {
    CardS,
  },
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
      require: true,
    },
    salary: {
      type: Number,
      require: true,
    },
    department: {
      type: String,
      require: true,
    },
    gender: {
      type: String,
    },
    skill: {
      type: Array,
    },
  },
  methods: {
    showDescription(id) {
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<style scoped>
li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background-color: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s linear;
}
</style>