<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <MyForm />
  </div>
</template>

<script>
import MyForm from "@/components/MyForm.vue";

export default {
  name: "HomeView",
  components: {
    MyForm,
  },
};
</script>
