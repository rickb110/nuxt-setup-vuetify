<template>
<div>
<v-container fluid grid-list-lg>
<GridCards/>

<div v-editable="blok" class="page">

       <v-toolbar color="indigo" dark>
        <v-toolbar-title>Get In Touch</v-toolbar-title>
        
      </v-toolbar>
	  
	  <v-card>
    <component :key="blok._uid" 
	v-for="blok in blok.body" 
	:blok="blok" 
	:is="blok.component"
	>
	
	</component>
	
	</v-card>

  </div>
  
</v-container>
 </div> 
  
</template>

<script>
import GridCards from '~/components/GridCards.vue'


export default {
  props: ['blok'],
  components: {
	GridCards
	}
}
</script>