<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Fb</span>
        <span class="font-weight-light">DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="/"
        target="_blank"
        @onclick="pannelHidden" 
      >do that: onclick display the pannel component -->
        <span class="mr-2">Account</span>
      </v-btn>
    </v-app-bar>

    <v-content>
      <NavDrawer class="float-right position-absolute"/>
      <Gallery />
    </v-content>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
import Gallery from './components/Gallery';
import NavDrawer from './components/NavDrawer';

export default {
  name: 'App',
  components: {
    NavDrawer,
    Gallery
  },
  data: () => ({
    
  }), 
};
</script>
