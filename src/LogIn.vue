<template>
   <div>
      
       <p> Zalogowany jako {{username}}  </p>
       <form>
       	
    	<button @click = "$emit('logout')"> wyloguj </button>
    	
    	<ol>
  		<li v-for="m in meetings" :key="m.id">{{ m }}</li>
		</ol>
    	
       </form>
       
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
 
}
</script>