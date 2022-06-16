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
      <v-app-bar-title class="text-no-wrap"
        >丰一帆 / Yifan Feng</v-app-bar-title
      >
      <v-spacer></v-spacer>
      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab @click="$vuetify.goTo('#bio')">About Me</v-tab>
          <v-tab @click="$vuetify.goTo('#news')">News</v-tab>
          <v-tab @click="$vuetify.goTo('#note')">Notes</v-tab>
          <v-tab @click="$vuetify.goTo('#service')">Services</v-tab>
          <v-tab @click="$vuetify.goTo('#publication')">Publications</v-tab>
          <v-tab @click="$vuetify.goTo('#dataset')">Datasets</v-tab>
          <v-tab @click="$vuetify.goTo('#toolbox')">Toolbox</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <v-container id="MyContent">
        <MyBio class="my-6" id="bio" />
        <v-divider></v-divider>
        <MyNews class="my-6" id="news"/>
        <v-divider></v-divider>
        <MyNote class="my-6" id="note" style="height: 500px" />
        <v-divider></v-divider>
        <MyService class="my-6" id="service"/>
        <v-divider></v-divider>
        <MyPublication class="my-6" id="publication" style="height: 500px" />
        <v-divider></v-divider>
        <MyDataset class="my-6" id="dataset" style="height: 500px" />
        <v-divider></v-divider>
        <MyToolbox class="my-6" id="toolbox" style="height: 500px" />
      </v-container>
    </v-main>

    <v-footer color="primary" dark padless>
      <v-container fluid class="pa-0">
        <v-row class="align-center" no-gutters>
          <v-col cols="12">
            <v-card-subtitle class="text-center pb-1 text-subtitle-1">
              <strong>Yifan Feng</strong>
            </v-card-subtitle>
            <v-card-text class="text-center">
              Copyright © 2022 -
              {{ new Date().getFullYear() }}, All rights reserved.
            </v-card-text>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
import MyBio from "./components/Bio";
import MyNews from "./components/News";
import MyService from "./components/Service";
import MyNote from "./components/Note";
import MyPublication from "./components/Publication";
import MyDataset from "./components/Dataset";
import MyToolbox from "./components/Toolbox";

export default {
  name: "App",

  components: {
    MyBio,
    MyNews,
    MyService,
    MyNote,
    MyPublication,
    MyDataset,
    MyToolbox,
  },

  data: () => ({
    //
  }),

  methods: {},
};
</script>
