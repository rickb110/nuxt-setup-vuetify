<template>
<v-container bg fill-height grid-list-md >
<v-layout row wrap align-center>
<v-flex>
<div v-editable="story.content" class="blog">
<v-card max-width='1000'>

	  <v-img contain :src="story.content.image"></v-img>
      <v-card-text><h1>{{ story.content.name }}</h1></v-card-text>
      <v-card-text><div class="blog__body" v-html="body">
      </div></v-card-text>
		
</v-card>
</div>
</v-flex>
</v-layout>
</v-container>
</template>

<script>
import marked from 'marked'
import storyblokLivePreview from '@/mixins/storyblokLivePreview'

export default {
  data () {
    return { story: { content: { body: '' } } }
  },
  computed: {
    body () {
      return marked(this.story.content.body)
    }
  },
  mixins: [storyblokLivePreview],
  asyncData (context) {
    let version = context.query._storyblok || context.isDev ? 'draft' : 'published'
    let endpoint = `cdn/stories/${context.params.language}/blog/${context.params.slug}`

    return context.app.$storyapi.get(endpoint, {
      version: version,
      cv: context.store.state.cacheVersion
    }).then((res) => {
      return res.data
    }).catch((res) => {
      context.error({ statusCode: res.response.status, message: res.response.data })
    })
  }
}
</script>


<style lang="scss">
.blog {
  padding: 0 20px;
  max-width: 800px;
  margin: 0px auto 100px;

  img {
    width: 100%;
    height: auto;
  }
}



.blog__body {
  line-height: 1.6;
}
</style>