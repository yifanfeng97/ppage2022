<template>
  <v-container>
    <v-dialog transition="dialog-top-transition" max-width="600">
      <template v-slot:activator="dialog">
        <v-card>
          <v-img
            :src="img_src"
            height="130"
            contain
            @click="dialog.value = true"
          >
          </v-img>
        </v-card>
      </template>
      <template v-slot:default="dialog">
        <v-card>
          <v-toolbar color="primary" dark>Illustration</v-toolbar>
          <v-img class="pa-12" :src="img_src" height="230" contain> </v-img>

          <v-card-actions class="justify-end">
            <v-btn text @click="dialog.value = false">Close</v-btn>
          </v-card-actions>
        </v-card>
      </template>
    </v-dialog>
  </v-container>
</template>

<script>
const Cite = require("citation-js");
export default {
  name: "MyPublication",
  created: function () {
    this.papers.sort(function (a, b) {
      return b.index - a.index;
    });
  },
  data: () => ({
    papers: "",
    cur_bibtex: "",
    cur_bibliography: "",
  }),
  methods: {
    select_paper: function (bib_tex) {
      let example = new Cite(Cite.util.fetchFile(bib_tex));
      this.cur_bibtex = example.format("bibtex", {
        format: "html",
      });
      this.cur_bibliography = example.format("bibliography", {
        format: "html",
      });
    },
  },
};
</script>
