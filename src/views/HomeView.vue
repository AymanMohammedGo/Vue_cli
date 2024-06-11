<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <MyComponent :name="name">
      <template #slotTitle>
        <h3>this is solt title</h3>
      </template>
      <template #slotText><p>this is solt paragraph</p></template>
    </MyComponent>
  </div>
</template>

<script>
import MyComponent from "@/components/MyComponent.vue";

export default {
  name: "HomeView",
  components: {
    MyComponent,
  },
  data() {
    return {
      name: "Ayman",
    };
  },
};
</script>
