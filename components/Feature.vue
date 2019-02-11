<template>
  <div v-editable="blok" class="util__flex-eq">
  <v-card>
    <v-container
                    fill-height
                    fluid
                    pa-2
                  >
    <h1>{{ blok.name }}</h1>
	</v-container>
	</v-card>
  </div>
</template>

<script>
export default {
  props: ['blok']
}
</script>