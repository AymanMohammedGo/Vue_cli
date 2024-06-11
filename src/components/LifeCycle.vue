<template>
  <div>
    <h3>Compnents Life Cycle Hook</h3>
    <h4>age is {{ age }}</h4>
    <button @click="age++">inc age</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Ahmad",
      age: "28",
    };
  },
  beforeCreate() {
    alert("BeforeCreate");
  },
  created() {
    alert("Create");
  },
  beforeMount() {
    alert("BeforeMount");
  },
  mounted() {
    alert("Mounted");
  },
  beforeUpdate() {
    alert("BeforeUpdate");
  },
  updated() {
    alert("Updated");
  },
  beforeUnmount() {
    alert("BeforeUnmount");
  },
  unmount() {
    alert("Unmount");
  },
};
</script>
