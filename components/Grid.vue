<template>
  <!--<div v-editable="blok" class="util__flex"> -->
  <div>
  <v-container
                    fill-height
                    fluid         					
                  >
	<v-layout row wrap>
    <!--//<component :key="blok._uid" v-for="blok in blok.columns" :blok="blok" :is="blok.component"></component> -->
	<v-flex 
	xs6
	>
	<v-card 
	flat>
	<NewsletterForm/>
	</v-card>
		<TwitterCard/>
	</v-flex>
	</v-layout>
	</v-container>
  </div>
</template>

<script>
import TwitterCard from '~/components/TwitterCard.vue'
import NewsletterForm from '~/components/NewsletterForm.vue'

export default {
  props: ['blok'],
  components: {
  TwitterCard,
  NewsletterForm
  }
}
</script>