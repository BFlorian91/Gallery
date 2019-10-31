<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <router-link tag="li" to="/">
          <button>
            <span>FB</span>
            <span class="font-weight-light">DESIGN</span>
          </button>
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-switch
        :label="`Dark Theme`"
        @change="$vuetify.theme.dark = !$vuetify.theme.dark"
        class="mt-6 mr-4"
      ></v-switch>
      <router-link tag="li" :to="{ name: 'signup' }">
        <v-btn>
          <span class="mr-2">Account</span>
        </v-btn>
      </router-link>
    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: "App",
  components: {},
  data: () => {
    return {};
  }
};
</script>

<style scoped>
li {
  list-style-type: none;
}
button:focus {
  outline: 0;
}
</style>