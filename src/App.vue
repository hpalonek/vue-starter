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
    <div v-if="isAuthenticated">
    	<p> Zalogowany jako {{email}} </p>
    	<button @click = "logMeOut()">Wyloguj </button>
      </div>
    <div v-else>
    	<input type ="text" v-model="email">
    	<button @click = "logMeIn()">Zaloguj sie</button>
    </div>
    
    
  <!--  
   <div v-if="email.length < 10">Ale masz krótki adres!</div>
	<div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
	<div v-else>Twój adres e-mail jest stanowczo za długi.</div>
  -->  
   	
    
  </div>
</template>


<script>
import "milligram";

export default{
	data() {
		  return {
		    email: '',
		    isAuthenticated: false
		  };
		},

	methods: {
		  logMeIn() {
		    this.isAuthenticated = true;
		  },
		  logMeOut() {
			    this.isAuthenticated = false;
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
