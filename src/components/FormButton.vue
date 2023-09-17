<template>
  <button class="button" :disabled="disabled">{{ text }}</button>
</template>
<script>
export default {
  props: {
    text: {
      String,
      required: true,
    },
    disabled: {
      type: Boolean,
      required: false,
    },
  },
};
</script>

<style scoped>
.button {
  display: black;
  width: 100%;
  height: 3rem;
  background: lightblue;
  color: #000;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
}

.button:hover {
  opacity: 0.7;
}
button:disabled {
  opacity: 0.5;
}
</style>
