<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <LifeCycle />
  </div>
</template>

<script>
import LifeCycle from "@/components/LifeCycle.vue";

export default {
  name: "HomeView",
  components: {
    LifeCycle,
  },
};
</script>
