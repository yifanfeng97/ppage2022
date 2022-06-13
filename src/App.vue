<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
      prominent
      shrink-on-scroll
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
    >
      <template v-slot:img="{ props }">
        <v-img v-bind="props"></v-img>
      </template>
      <!-- gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)" -->
      <v-app-bar-title class="text-no-wrap">丰一帆 / Yifan Feng</v-app-bar-title>
      <v-spacer></v-spacer>
      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab>About Me</v-tab>
          <v-tab>Research</v-tab>
          <v-tab>Publications</v-tab>
          <v-tab>Datasets</v-tab>
          <v-tab>Toolbox</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <v-container class="overflow-y-auto" max-height="600">
        <HelloWorld style="height: 2000px" />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
