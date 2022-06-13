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
          <v-tab @click="tinyGo('#bio')">About Me</v-tab>
          <v-tab @click="tinyGo('#research')">Research</v-tab>
          <v-tab @click="tinyGo('#publication')">Publications</v-tab>
          <v-tab @click="tinyGo('#dataset')">Datasets</v-tab>
          <v-tab @click="tinyGo('#toolbox')">Toolbox</v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <v-container  id="MyContent" >
        <MyBio id="bio" style="height: 500px" />
        <v-divider></v-divider>
        <MyResearch id="research" style="height: 500px" />
        <v-divider></v-divider>
        <MyPublication id="publication" style="height: 500px" />
        <v-divider></v-divider>
        <MyDataset id="dataset" style="height: 500px" />
        <v-divider></v-divider>
        <MyToolbox id="toolbox" style="height: 500px" />
        <v-divider></v-divider>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import MyBio from "./components/Bio";
import MyResearch from "./components/Research";
import MyPublication from "./components/Publication";
import MyDataset from "./components/Dataset";
import MyToolbox from "./components/Toolbox";

export default {
  name: "App",

  components: {
    MyBio,
    MyResearch,
    MyPublication,
    MyDataset,
    MyToolbox,
  },

  data: () => ({
    //
  }),

  methods: {
    tinyGo(name) {
      window.location.href = name;
    },
  },
};
</script>
