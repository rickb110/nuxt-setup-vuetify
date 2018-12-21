<template>
<div>

<v-app>
<top-header/>
 
<v-content>
      <v-container>
	  
        <nuxt />
      </v-container>
</v-content>
 
   
 <bottom-footer/>
  </v-app>
 
  </div>
</template>

<script>
import TopHeader from '~/components/TopHeader.vue'
import BottomFooter from '~/components/BottomFooter.vue'

export default {
  components: {
    TopHeader,
    BottomFooter
  }
}


</script>

<style lang="scss">
@import '../assets/scss/styles.scss';


</style>
