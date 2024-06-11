<template>
  <div>
    <h2>My Name is {{ name }}</h2>
    <input type="text" />
  </div>
</template>
<script>
export default {
  props: {
    name: {
      type: String,
    },
  },
};
</script>
