<template>
  <v-app>
    <MyHeader :area="cur_area" />

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
        <MyPublication
        class="my-6"
        id="publication"
        v-intersect="changeCurrentTab"
        />
        <v-divider></v-divider>
        <MyService class="my-6" id="service" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <MyDataset class="my-6" id="dataset" v-intersect="changeCurrentTab" />
        <v-divider></v-divider>
        <MyToolbox class="my-6" id="toolbox" v-intersect="changeCurrentTab" />
      </v-container>
      <v-responsive height="200"> </v-responsive>
    </v-main>

    <MyFooter />
  </v-app>
</template>

<script>
import MyHeader from "@/components/Header.vue";
import MyFooter from "@/components/Footer.vue";
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
    MyHeader,
    MyFooter,
    MyBio,
    MyNews,
    MyService,
    // MyNote,
    MyPublication,
    MyDataset,
    MyToolbox,
  },

  data: () => ({
    cur_area: 0,
  }),

  methods: {
    changeCurrentTab(entries) {
      if (entries[0].isIntersecting) {
        if (entries[0].target.id == "bio") {
          this.cur_area = 0;
        } else if (entries[0].target.id == "news") {
          this.cur_area = 1;
        } else if (entries[0].target.id == "publication") {
          this.cur_area = 2;
        } else if (entries[0].target.id == "service") {
          this.cur_area = 3;
        } else if (entries[0].target.id == "dataset") {
          this.cur_area = 4;
        } else if (entries[0].target.id == "toolbox") {
          this.cur_area = 5;
        }
      }
    },
  },
};
</script>
