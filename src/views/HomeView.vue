<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <KeepAlive>
      <HelloWorld :name="name" v-if="!isShow" />
    </KeepAlive>
  </div>
  <div><button @click="isShow = !isShow">change state</button></div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
  data() {
    return {
      name: "Ayman",
      isShow: true,
    };
  },
};
</script>
