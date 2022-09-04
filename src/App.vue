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
        <v-tabs align-with-title v-model="current_area">
          <v-tab @click="$vuetify.goTo('#bio')">About Me</v-tab>
          <v-tab @click="$vuetify.goTo('#news')">News</v-tab>
          <!-- <v-tab @click="$vuetify.goTo('#note')">Notes</v-tab> -->
          <v-tab @click="$vuetify.goTo('#service')">Services</v-tab>
          <v-tab @click="$vuetify.goTo('#publication')">Publications</v-tab>
          <v-tab @click="$vuetify.goTo('#dataset')">Datasets</v-tab>
          <v-tab @click="$vuetify.goTo('#toolbox')">Toolbox</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <v-container id="MyContent">
        <MyBio class="my-6" id="bio" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <MyNews class="my-6" id="news" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <!-- <template v-if="false">
          <MyNote
            class="my-6"
            id="note"
            style="height: 500px"
            v-intersect="changeCurrentTab"
          />
          <v-divider></v-divider>
        </template> -->
        <MyService class="my-6" id="service" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <MyPublication
          class="my-6"
          id="publication"
          v-intersect="changeCurrentTab"
        />
        <v-divider></v-divider>
        <MyDataset class="my-6" id="dataset" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <MyToolbox class="my-6" id="toolbox" v-intersect="changeCurrentTab" />
      </v-container>
      <v-responsive height="200"> </v-responsive>
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
// import MyNote from "./components/Note";
import MyPublication from "./components/Publication";
import MyDataset from "./components/Dataset";
import MyToolbox from "./components/Toolbox";

export default {
  name: "App",

  components: {
    MyBio,
    MyNews,
    MyService,
    // MyNote,
    MyPublication,
    MyDataset,
    MyToolbox,
  },

  data: () => ({
    current_area: 0,
  }),

  methods: {
    changeCurrentTab(entries) {
      if (entries[0].isIntersecting) {
        if (entries[0].target.id == "bio") {
          this.current_area = 0;
        } else if (entries[0].target.id == "news") {
          this.current_area = 1;
        } else if (entries[0].target.id == "service") {
          this.current_area = 2;
        } else if (entries[0].target.id == "publication") {
          this.current_area = 3;
        } else if (entries[0].target.id == "dataset") {
          this.current_area = 4;
        } else if (entries[0].target.id == "toolbox") {
          this.current_area = 5;
        }
      }
    },
  },
};
</script>
