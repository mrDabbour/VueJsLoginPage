<template>
  <h1>Login Form using VueJs</h1>

  <form class="form">
    <form-input
      :value="username.value"
      :error="username.error"
      :rules="username.rules"
      type="text"
      name="Username"
      @updateValue="update"
    ></form-input>
    <form-input
      :value="password.value"
      :error="password.error"
      :rules="password.rules"
      type="password"
      name="Password"
    ></form-input>
    <form-button text="Login Now" :disabled="!isValid"></form-button>
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
  data() {
    return {
      username: {
        value: "name",
        rules: {
          required: true,
          min: 6,
        },
        error: "",
      },
      password: {
        value: "12345678",
        rules: {
          required: true,
          min: 8,
        },
        error: "",
      },
    };
  },
  methods:{
    update(value){
      console.log(`from app.vue`);
      console.log(value);
    },
  },
  computed: {
    isValid() {
      return !this.username.error && !this.password.error;
    },
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
