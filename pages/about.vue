<template>
<v-container bg fill-height grid-list-md >
<v-layout row wrap align-center>
<v-flex>
<div class="blog">
<v-card max-width='1000'>

      <v-container
        fluid
        grid-list-lg
      >
	  <v-card-title primary-title><h1>About Me</h1></v-card-text></v-card-title>
        <v-layout row wrap>
          <v-flex xs16>
			<v-flex xs8>	
				<v-img src="/richard.jpg" aspect-ratio="1.2" max-width="300" ></v-img>
			</v-flex>
	  <v-spacer></v-spacer>
	<v-divider light></v-divider>
<v-card-text>

<p> I am a Google Gold Product Expert who works with clients of all sizes to help them achieve a sustained web presence. <a href="https://topcontributor.withgoogle.com/profile/richard-barrett-e2051a">View my Google Profile & Answers</a> </p>
<p>I have been working as an SEO since 2011 where as a junior developer I took over the technical SEO for the large affiliate marketer TopCashback and over time increased my understanding of all aspects of SEO before taking control of all SEO for the company.</p>


<p>I moved on to Prospects which operates as the commercial arm of the research chartiy HECSU where I assisted them in a massive site migration.</p>


<p>I currently work for ICG as their PPC & SEO specialist, a full stack agency located in Warton, Lancashire</p>


<p>I am a big fan of animals so if you are a Zoo or Aquarium looking for SEO advice please get in touch!</p>



</v-card-text>
          </v-flex>
        </v-layout>
      </v-container>	
</v-card>
</div>
</v-flex>
</v-layout>
</v-container>
</template>

<script>

export default {
  data () {
    
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