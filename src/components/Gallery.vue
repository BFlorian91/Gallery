<template>
  <v-row class="mt-4">
    <v-col cols="12" sm="10" offset-sm="1">
      <v-card>
        <v-container fluid>
          <v-row>
            <v-col v-for="n in 19" :key="n" class="d-flex child-flex" cols="4">
              <v-card flat tile class="d-flex">
                <v-img
                  :src="`https://picsum.photos/1920/1080?image=${n * 2 + 5}`"
                  :lazy-src="`https://picsum.photos/10/6?image=${n * 2 + 5}`"
                  aspect-ratio="1"
                  class="grey lighten-2"
                >
                  <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                </v-img>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: ["id"]
};
</script>

<style>
</style>
