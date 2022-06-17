<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">Publications</p>
    </v-row>
    <v-row>
      <v-col cols="12" class="my-2" v-for="p in papers" :key="p.index">
        <v-row>
          <v-col md="8" cols="12">
            <v-row class="d-flex align-center">
              <span class="text-subtitle-1 font-weight-bold">
                {{ p.title }}</span
              >
              <span class="text-subtitle-2 pl-2">{{ p.publication }}</span>
            </v-row>
            <v-row>
              <span class="text-body-1 font-italic grey--text text--darken-1">{{
                p.authors
              }}</span>
            </v-row>
            <v-row class="pt-2">
              <v-btn
                v-if="p.url_pdf != ''"
                x-small
                outlined
                color="primary"
                class="mr-1"
                :href="p.url_pdf"
                target="_blank"
              >
                PDF
              </v-btn>
              <v-btn
                v-if="p.url_code != ''"
                x-small
                outlined
                color="primary"
                class="mr-1"
                :href="p.url_code"
                target="_blank"
              >
                Code
              </v-btn>
              <v-dialog transition="dialog-bottom-transition" max-width="800">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    x-small
                    outlined
                    color="primary"
                    v-bind="attrs"
                    v-on="on"
                    class="mr-1"
                    @click="select_paper(p.bib_tex)"
                  >
                    Cite
                  </v-btn>
                </template>
                <template v-slot:default="dialog">
                  <v-card>
                    <v-toolbar
                      color="primary"
                      dark
                      class="text-h5 d-flex justify-center"
                      ><span>Cite This Paper!</span></v-toolbar
                    >
                    <v-container class="pa-12">
                      <v-row>
                        <v-row dense no-gutters class="mb-6">
                          <v-col cols="12">
                            <span class="text-h6"> APA: </span>
                          </v-col>
                          <v-col cols="12">
                            <span v-html="cur_bibliography"></span>
                          </v-col>
                        </v-row>
                        <v-divider dark></v-divider>
                        <v-row dense no-gutters>
                          <v-col cols="12" class="text-h6"> BibTex: </v-col>
                          <v-col cols="12">
                            <span v-html="cur_bibtex"></span>
                          </v-col>
                        </v-row>
                      </v-row>
                    </v-container>
                    <v-card-text> </v-card-text>
                    <v-card-actions class="justify-end">
                      <v-btn text @click="dialog.value = false">Close</v-btn>
                    </v-card-actions>
                  </v-card>
                </template>
              </v-dialog>
            </v-row>
          </v-col>
          <v-col md="4" cols="12"> Figure </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
const Cite = require("citation-js");
export default {
  name: "MyPublication",
  created: function () {
    // var example = new Cite("10.5281/zenodo.1005176");
    // let a = Cite.util.fetchFile("../assets/publication/2018-hgnn/cite.bib");
    let a = Cite.util.fetchFile("publication/2018-hgnn/cite.bib");
    console.log(a);
    var example = new Cite(
      Cite.util.fetchFile("publication/2018-hgnn/cite.bib")
    );
    let output = example.format("bibliography", {
      // format: "html",
    });
    console.log(output);
  },
  data: () => ({
    papers: [
      {
        index: 1,
        title:
          "GVCNN: Group-view Convolutional Neural Networks for 3D Shape Recognition.",
        publication: "CVPR 2018.",
        authors:
          "Yifan Feng, Zizhao Zhang, Xibin Zhao, Rongrong Ji and Yue Gao*.",
        url_pdf:
          "http://openaccess.thecvf.com/content_cvpr_2018/papers/Feng_GVCNN_Group-View_Convolutional_CVPR_2018_paper.pdf",
        url_code: "",
        bib_tex: "publication/2018-gvcnn/cite.bib",
        fw_path: "publication/2018-gvcnn/fw.png",
      },
      {
        index: 2,
        title: "Hypergraph Neural Networks.",
        publication: "AAAI 2018.",
        authors:
          "Yifan Feng, Haoxuan You, Zizhao Zhang, Rongrong Ji and Yue Gao*.",
        url_pdf:
          "https://www.aaai.org/ojs/index.php/AAAI/article/download/4235/4113",
        url_code: "https://github.com/iMoonLab/HGNN",
        bib_tex: "publication/2018-hgnn/cite.bib",
        fw_path: "publication/2018-hgnn/fw.png",
      },
    ],
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
