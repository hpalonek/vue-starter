<template>
   <div>
      
       <p> Zalogowany jako {{username}}  </p>
       
       	
    	<button @click = "$emit('logout')"> wyloguj </button>
    	
    	<ol>
  		<li v-for="m in meetings" :key="m.id">{{ m }}</li>
		</ol>
		
		<button @click = dodaj()> dodaj spotkanie </button>
    	
    	
      
       
   </div>
</template>

<script>
export default {
	props: ['username'],

	data(){
		return{
			meetings: [
				'MWO',
				'to',
				'bu'
			]
		}
	},
	
	methods: {
		dodaj(){
			this.meetings.push('nowe');
		}
	}
 
}
</script>