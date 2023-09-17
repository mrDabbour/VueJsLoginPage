<template>
  <div class="form-labels">
    <label class="form-label" :for="name">{{ name }}</label>
    <div class="form-error">{{ errorMessage }}</div>
  </div>
  <input :value="inputValue" @input="input" class="form-input" :type="type" :id="name" />
</template>

<script>
export default {
  emits: [`updateValue`],
  props: {
    value: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      default() {
        return "text";
      },
    },
    rules: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    input($event) {
      this.$emit("updateValue", {
        value: $event.target.value,
      });
      this.inputValue = $event.target.value;
      console.log($event.target.value);
    },
  },
  computed: {
    errorMessage() {
      if (this.rules.required && this.inputValue.length === 0) {
        return "Required";
      }
      if (this.rules.min && this.inputValue.length < this.rules.min) {
        return `Min length is ${this.rules.min}`;
      } else {
        return "";
      }
    },
  },
};
</script>

<style scoped>
.form-labels {
  display: flex;
  justify-content: space-between;
}

.form-error {
  color: tomato;
  cursor: pointer;
}

.form-input {
  outline: none;
  border: none;
  background: white;
  color: #000;
  padding: 0.7rem;
  margin: 1rem 0;
  border-radius: 8px;
}
</style>
