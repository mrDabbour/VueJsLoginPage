<template>
  <h1>Login Form using VueJs</h1>

  <form class="form">
    <form-input :rules="username.rules" type="text" name="Username"></form-input>
    <form-input :rules="password.rules" type="password" name="Password"></form-input>
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
  data(){
    return{
      username:{
        rules:{
          required:true,
          min:6,
        },
      },
      password:{
        rules:{
          required:true,
          min:8,
        },
      },
    };
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
