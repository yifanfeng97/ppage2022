<template>
  <div>
    <v-app-bar
      app
      color="primary"
      dark
      prominent
      shrink-on-scroll
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
    >
      <v-app-bar-nav-icon
        v-if="$vuetify.breakpoint.mobile"
        @click="drawer = true"
      ></v-app-bar-nav-icon>
      <template v-slot:img="{ props }">
        <v-img v-bind="props"></v-img>
      </template>
      <v-app-bar-title class="text-no-wrap"
        >丰一帆 / Yifan Feng</v-app-bar-title
      >
      <v-spacer></v-spacer>
      <template v-if="!$vuetify.breakpoint.mobile" v-slot:extension>
        <v-tabs align-with-title v-model="cur_area">
          <v-tab
            v-for="item in items"
            :key="item.id"
            @click="$vuetify.goTo(item.tag)"
          >
            {{ item.title }}
          </v-tab>
          <!-- <v-tab @click="$vuetify.goTo('#bio')">About Me</v-tab>
          <v-tab @click="$vuetify.goTo('#news')">News</v-tab>
          <v-tab @click="$vuetify.goTo('#service')">Services</v-tab>
          <v-tab @click="$vuetify.goTo('#publication')">Publications</v-tab>
          <v-tab @click="$vuetify.goTo('#dataset')">Datasets</v-tab>
          <v-tab @click="$vuetify.goTo('#toolbox')">Toolbox</v-tab> -->
        </v-tabs>
      </template>
    </v-app-bar>
    <v-navigation-drawer app v-model="drawer" temporary>
      <v-list nav>
        <v-list-item-group active-class="deep-purple--text text--accent-4" v-model="cur_area">
          <v-list-item
            v-for="item in items"
            :key="item.id"
            class="text-subtitle-1 font-weight-bold"
            @click="$vuetify.goTo(item.tag)"
          >
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title class="text-h6">{{
              item.title
            }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "MyHeader",
  props: {
    area: {
      type: Number,
      default: 0,
    },
  },

  computed: {
    cur_area: {
      get() {
        return this.area;
      },
      set(val) {
        this.$emit("update:area", val);
      },
    },
  },

  data: () => ({
    drawer: false,
    items: [
      { id: 0, title: "About Me", icon: "mdi-account", tag: "#bio" },
      { id: 1, title: "News", icon: "mdi-newspaper", tag: "#news" },
      // { id:2, title: "Notes", icon: "mdi-notebook", tag: "#note" },
      { id: 3, title: "Services", icon: "mdi-cog", tag: "#service" },
      { id: 4, title: "Publications", icon: "mdi-book", tag: "#publication" },
      { id: 5, title: "Datasets", icon: "mdi-database", tag: "#dataset" },
      { id: 6, title: "Toolbox", icon: "mdi-wrench", tag: "#toolbox" },
    ],
  }),
};
</script>
