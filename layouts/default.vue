<template>
<div>

<v-app light>
<top-header/>
 
<v-content>
      <v-container>
	  
        <nuxt />
      </v-container>
    </v-content>
 
   

  </v-app>
  <bottom-footer/>
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
