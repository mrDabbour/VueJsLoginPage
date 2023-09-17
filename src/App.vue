<template>
  <h1>Login Form using VueJs</h1>

  <form class="form">
    <form-input></form-input>
    <form-input></form-input>
    <form-button text="Login Now" :disabled="false"></form-button>
  </form>
</template>

<script>
import FormInput from "./components/FormInput.vue";
import FormButton from "./components/FormButton.vue";
export default {
  name: "App",
  components: {
    FormInput,
    FormButton,
  },
};
</script>

<style>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.form {
  background: linear-gradient(65deg, #e6e6e6, lightgreen);
  padding: 2rem;
  border-radius: 15px;
}
</style>
