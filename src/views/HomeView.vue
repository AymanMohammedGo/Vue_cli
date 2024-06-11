<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld @updateActive="changeActive" :isActive="isActive" />
    <!-- <HelloWorld
      @updateActive="($event) => changeActive($event)"
      :isActive="isActive"
    /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
  data() {
    return {
      isActive: true,
    };
  },
  methods: {
    changeActive() {
      this.isActive = !this.isActive;
    },
    // changeActive(data) {
    //   this.isActive = data;
    // },
  },
};
</script>
