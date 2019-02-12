<template>
  
    <v-layout row wrap>
		
      <v-flex d-flex xs12 sm6 md8>
        <v-card color="indigo" dark>

          <v-card-title primary class="title">Richard Barrett SEO & PPC Specialist</v-card-title>
          <v-card-text>{{ Intro }}</v-card-text>

        </v-card>
      </v-flex>
      <v-flex d-flex xs12 sm6 md3>
        <v-layout row wrap>
          <v-flex d-flex>
            <v-card color="green" dark>

			<v-card-title primary class="title">Tools</v-card-title>

              <v-card-text>{{ tools }}</v-card-text>
	
            </v-card>
          </v-flex>
          <v-flex d-flex>
            <v-layout row wrap>
              <v-flex
                d-flex
                xs12
              >
                <v-card
                  color="blue lighten-2"
                  dark
                >
				<v-card-title primary class="title">Latest Blog</v-card-title>
                  <v-card-text>{{ blog }}</v-card-text>
                </v-card>
              </v-flex>

            </v-layout>
          </v-flex>
        </v-layout>
      </v-flex>

    </v-layout>
 
</template>

<script>
  export default {
    data: () => ({
      Intro: 'I run & optimise campaigns for companies of all sizes & budgets, helping them reach their target audiences. I also offer free support for websites via the Google Webmaster Forum where I am a Gold Product Expert',
	  tools: 'Find & Download useful tools from around the web',
	  blog: 'View my Latest Blog'
    })
  }
</script>