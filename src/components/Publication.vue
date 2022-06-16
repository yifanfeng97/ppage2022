<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">Publications</p>
    </v-row>
    <v-row>
      <v-col cols="12" v-for="p in papers" :key="p.index">
        {{p.title}}
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
    var example = new Cite(Cite.util.fetchFile("publication/2018-hgnn/cite.bib"));
    let output = example.format("bibliography", {
      // format: "html",
      template: "apa",
      lang: "en-US",
    });
    console.log(output);
  },
  data: () => ({
    papers: [
      {
        index: 1,
        title:
          "GVCNN: Group-view Convolutional Neural Networks for 3D Shape Recognition",
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
        title: "Hypergraph Neural Networks",
        authors:
          "Yifan Feng, Haoxuan You, Zizhao Zhang, Rongrong Ji and Yue Gao*.",
        url_pdf:
          "https://www.aaai.org/ojs/index.php/AAAI/article/download/4235/4113",
        url_code: "https://github.com/iMoonLab/HGNN",
        bib_tex: "publication/2018-hgnn/cite.bib",
        fw_path: "publication/2018-hgnn/fw.png",
      },
    ],
  }),
};
</script>
