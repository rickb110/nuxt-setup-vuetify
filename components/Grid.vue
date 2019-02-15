<template>
  <!--<div v-editable="blok" class="util__flex"> -->
 
  <v-container
                    fill-height
                    fluid
					grid-list-lg
                  >
	<v-layout row>
    <!--//<component :key="blok._uid" v-for="blok in blok.columns" :blok="blok" :is="blok.component"></component> -->

	<v-card 
	flat>
	<NewsletterForm/>
	</v-card>
	<v-spacer></v-spacer>
		<TwitterCard/>

	</v-layout>
	</v-container>
 
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