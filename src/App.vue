<!--

<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

-->

<template>
  <div>
    <h1> Witaj w systemie </h1>
    <div v-if="email.length > 0">
    	<log-in :username = "email" @logout="logMeOut()"></log-in>
    	
      </div>
    <div v-else>
    	<login-form @login="logMeIn($event)" button-label = "wbijam" header = "Zaloguj sie"></login-form>
    	
    </div>
    
    
  <!--  
   <div v-if="email.length < 10">Ale masz krótki adres!</div>
	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
	<div v-else>Twój adres e-mail jest stanowczo za długi.</div>
	
	<p> Zalogowany jako {{email}} </p>
    	<button @click = "logMeOut()">Wyloguj </button>
  -->  
   	
    
  </div>
</template>


<script>
import "milligram";
import LoginForm from "./LoginForm";
import LogIn from "./LogIn";

export default{
	components: {LoginForm, LogIn},
	
	data() {
		  return {
		    email: '',
		    //isAuthenticated: false
		  };
		},

	methods: {
		  logMeIn(username) {
		    //this.isAuthenticated = true;
		    this.email = username
		  },
		  logMeOut() {
			    //this.isAuthenticated = false;
			    this.email = '';
			  }
		},

}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
