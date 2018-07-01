<template>
  <div class="register_form">
    <h1>Register</h1>
    <input type="email" name="email" placeholder="Email" v-model="email">
    <input type="password" name="password" placeholder="Password" v-model="password">
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .register_form {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .register_form input {
    margin: 1rem;
    border: 1px solid black;
    padding: 1rem;
  }

  .register_form button {
    padding: 1rem;
    width: 10rem;
    border-radius: 5px;
  }

</style>
