<template>
<header class="top-header util__flex util__container">
    <v-navigation-drawer
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app
    >
	
	
      <v-list>
        <v-list-tile
          v-for="(navitem, index) in $store.state.settings.main_navi"
          :to="navitem.link.cached_url"
          :key="index"
          router
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="navitem.icon" />
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="navitem.name" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
	
	
	
	
    <v-toolbar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-toolbar-side-icon @click="drawer = !drawer" />
      


	  
	  
      <v-toolbar-title v-text="title"/>
	  <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down" 
		v-for="(navitem, index) in $store.state.settings.main_navi"
          :to="navitem.link.cached_url"
          :key="index"
          router
          exact
		>
	  
      <v-btn 
	  v-text="navitem.name" 
	  :color="navitem.colour"
	  :href="navitem.link.cached_url"
	  depressed></v-btn>
    </v-toolbar-items>
    </v-toolbar>
	</header>
</template>

<script>
  export default {
    data() {
      return {
        clipped: false,
        drawer: false,
        fixed: false,
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'General Title Goes Here'
      }
    }
  }
</script>

<style lang="scss">
  .top-header {
    justify-content: space-between;
    padding-top: 30px;
    padding-bottom: 30px;
  }

  .top-header__logo {
    text-align: center;
    position: absolute;
    left: 50%;

    img {
      position: relative;
      max-height: 60px;
      left: -50%;
      top: -15px;
    }
  }

  .top-header__second-navi {
    text-align: right;
  }
</style>