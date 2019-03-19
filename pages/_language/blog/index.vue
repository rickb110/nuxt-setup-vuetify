<template>
<v-layout align-center justify-center>
<v-card max width='1200'>
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
						dark
						:to="'/' + blogPost.full_slug"
						:color=whichColor()
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
</v-layout>
</template>

<script>
export default {
  data () {
    return { 
total: 0,
data: { stories: [] },
colors: ['indigo', 'red lighten-2', 'green lighten-2', 'blue lighten-2', 'teal' ],
colorpos: 0
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
  },
  methods: {
  whichColor() {
  var position = this.colorpos + 1
  if (position > this.colors.length) {
  position = 1
  }
  this.colorpos = position
  return this.colors[(position - 1)]

  }
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