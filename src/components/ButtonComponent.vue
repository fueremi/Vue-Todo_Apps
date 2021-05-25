<template>
  <button class="btn" :style="{ background, color }">
    {{ title }}
  </button>
</template>

<script>
export default {
  name: "ButtonComponent",
  props: {
    title: {
      type: String,
      default: "Please add attribute [background, title, color] on Tag",
    },
    background: {
      type: String,
      default: "salmon",
    },
    color: {
      type: String,
      default: "#FFF",
    },
  },
};
</script>