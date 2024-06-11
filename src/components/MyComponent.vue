<template>
  <div class="parent">
    <h2>This is solt component {{ name }}</h2>
    <slot name="slotTitle"></slot>
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
