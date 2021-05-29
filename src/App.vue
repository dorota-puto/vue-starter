<template>

  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="authenticatedEmail == ''">
      <span>Zaloguj się e-mailem </span>
      <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
  </div>

  <div v-else>
    <h2>Witaj {{email}}</h2>
    <button @click="logOut()">Wyloguj</button>
    </div>
  </div>

</template>


<script>
import "milligram";

export default {
  data() {
  return {
    email: '',
    password: '',
    authenticatedEmail: ''
  };
},
methods: {
  logIn() {
    this.authenticatedEmail=this.email;
  },
  logOut() {
    this.authenticatedEmail = '';
  }
}
};
</script>

<style>

</style>
