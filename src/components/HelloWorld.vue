<template>
  <div>
    <p>active is : {{ isActive }}</p>
    <button @click="changeActive">change</button>
  </div>
</template>

<script>
export default {
  props: {
    isActive: {
      type: Boolean,
    },
  },

  methods: {
    changeActive() {
      this.$emit("updateActive");
      // this.$emit("updateActive", false);
    },
  },
};
</script>
