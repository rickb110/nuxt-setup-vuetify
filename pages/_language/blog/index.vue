<template>
<v-card>
<v-container>
<v-layout>

	<v-flex column row wrap>
		<div class="blog__overview">
		
		<v-card max-width='800' >
		<v-container>
		<v-img
			src='/tiles.jpg'
			aspect-ratio="1.5"
			></v-img>
				<v-title>What impact is internal linking having on your website</v-title>
		</v-container>
		</v-card>
		</div>

	
		
			<v-container>
			<section class="util__container">
				<div :key="blogPost.content._uid" v-for="blogPost in data.stories" class="blog__overview">
					<v-card
						hover
						raised
						:to="'/' + blogPost.full_slug"
						:color="blogPost.Colour"
						>
					
						<v-container>
						<h2>
						
						{{ blogPost.content.name }}
						
						</h2>
						<small>
						{{ blogPost.content.PublishDate }}
						</small>
						<p>
						{{ blogPost.content.intro }}
						</p>
						</v-container>
						
					</v-card>
				</div>
			</section>
			</v-container>
		
		
	</v-flex>
	
</v-layout>
</v-container>
</v-card>
</template>

<script>
export default {
  data () {
    return { 
		total: 0, data: { stories: [] }
		
		}
  },
  asyncData (context) {
    let version = context.query._storyblok || context.isDev ? 'draft' : 'published'

    return context.app.$storyapi.get('cdn/stories', {
      version: version,
      starts_with: `${context.store.state.language}/blog`,
      cv: context.store.state.cacheVersion
    }).then((res) => {
      return res
    }).catch((res) => {
      context.error({ statusCode: res.response.status, message: res.response.data })
    })
  }
}
</script>

<style lang="scss">
.blog__overview {
  padding: 0 20px;
  max-width: 600px;
  margin: 40px auto 60px;

  p {
    line-height: 1.6;
  }
}

.blog__detail-link {
  color: #000;
}
</style>