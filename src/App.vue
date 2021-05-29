<template>

  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="authenticatedUsername == ''">
      <login-form @login="logMeIn($event)"></login-form> 
  </div>

  <div v-else>
    <h2>Witaj {{authenticatedUsername}}</h2>
    <button @click="logOut()">Wyloguj</button>
    <meeting-page></meeting-page>>
    </div>
  </div>

</template>


<script>
import 'milligram'
import LoginForm from "./LoginForm";
import MeetingPage from "./meetings/MeetingPage";


export default {
  components: {LoginForm, MeetingPage},

  data() {
  return {
    authenticatedUsername: ''
  };
},
methods: {
  logMeIn(username) {
  this.authenticatedUsername = username;
  },
  logOut() {
    this.authenticatedUsername = '';
  }
}
};
</script>

<style>

</style>
