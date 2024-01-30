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
              <span class="text-h6 font-weight-medium"> {{ p.title }}. </span>
              <span class="text-h6 font-italic font-weight-regular pl-1">
                👉🏼 {{ p.publication }}</span
              >
            </v-row>
            <v-row>
              <span class="text-body-1 font-italic grey--text text--darken-1">
                {{ p.authors }}
              </span>
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
                    v-if="p.bib_tex != ''"
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
                        <v-row dense no-gutters>
                          <v-col cols="12" class="text-h6"> BibTex: </v-col>
                          <v-col cols="12">
                            <span v-html="cur_bibtex"></span>
                          </v-col>
                        </v-row>
                      </v-row>
                    </v-container>
                    <v-card-actions class="justify-end">
                      <v-btn text @click="dialog.value = false">Close</v-btn>
                    </v-card-actions>
                  </v-card>
                </template>
              </v-dialog>
            </v-row>
          </v-col>
          <v-col xl="2" lg="3" md="4" cols="12" class="pa-md-0">
            <v-card>
              <v-img :src="p.fw_path" height="130" contain> </v-img>
            </v-card>
          </v-col>
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
    this.papers.sort(function (a, b) {
      return b.index - a.index;
    });
  },
  data: () => ({
    papers: [
      {
        index: 1,
        title:
          "GVCNN: Group-view Convolutional Neural Networks for 3D Shape Recognition",
        publication: "CVPR 2018",
        authors:
          "Yifan Feng, Zizhao Zhang, Xibin Zhao, Rongrong Ji and Yue Gao*",
        url_pdf:
          "http://openaccess.thecvf.com/content_cvpr_2018/papers/Feng_GVCNN_Group-View_Convolutional_CVPR_2018_paper.pdf",
        url_code: "",
        bib_tex: "publication/2018-gvcnn/cite.bib",
        fw_path: "publication/2018-gvcnn/fw.png",
      },
      {
        index: 2,
        title:
          "PVNet: A Joint Convolutional Network of Point Cloud and Multi-View for 3D Shape Recognition",
        publication: "MM 2018",
        authors: "Haoxuan You, Yifan Feng, Rongrong Ji and Yue Gao*",
        url_pdf: "https://arxiv.org/pdf/1808.07659",
        url_code: "https://github.com/Hxyou/HLWD",
        bib_tex: "publication/2018-pvnet/cite.bib",
        fw_path: "publication/2018-pvnet/fw.png",
      },
      {
        index: 3,
        title: "Hypergraph Neural Networks",
        publication: "AAAI 2019",
        authors:
          "Yifan Feng, Haoxuan You, Zizhao Zhang, Rongrong Ji and Yue Gao*",
        url_pdf:
          "https://www.aaai.org/ojs/index.php/AAAI/article/download/4235/4113",
        url_code: "https://github.com/iMoonLab/HGNN",
        bib_tex: "publication/2019-hgnn/cite.bib",
        fw_path: "publication/2019-hgnn/fw.png",
      },
      {
        index: 4,
        title:
          "PVRNet: Point-View Relation Neural Network for 3D Shape Recognition",
        publication: "AAAI 2019",
        authors:
          "Haoxuan You, Yifan Feng, Xibin Zhao, Changqing Zou, Rongrong Ji and Yue Gao*",
        url_pdf:
          "https://www.aaai.org/ojs/index.php/AAAI/article/view/4945/4818",
        url_code: "https://github.com/iMoonLab/PVRNet",
        bib_tex: "publication/2019-pvrnet/cite.bib",
        fw_path: "publication/2019-pvrnet/fw.png",
      },
      {
        index: 5,
        title: "MeshNet: Mesh Neural Network for 3D Shape Representation",
        publication: "AAAI 2019",
        authors:
          "Yutong Feng, Yifan Feng, Haoxuan You, Xibin Zhao and Yue Gao*",
        url_pdf:
          "https://www.aaai.org/ojs/index.php/AAAI/article/view/4840/4713",
        url_code: "https://github.com/iMoonLab/MeshNet",
        bib_tex: "publication/2019-meshnet/cite.bib",
        fw_path: "publication/2019-meshnet/fw.png",
      },
      {
        index: 6,
        title: "Dynamic Hypergraph Neural Networks",
        publication: "IJCAI 2019",
        authors:
          "Jianwen Jiang, Yuexuan wei, Yifan Feng, Jingxuan Cao and Yue Gao*",
        url_pdf: "https://www.ijcai.org/Proceedings/2019/0366.pdf",
        url_code: "https://github.com/iMoonLab/DHGNN",
        bib_tex: "publication/2019-dhgnn/cite.bib",
        fw_path: "publication/2019-dhgnn/fw.png",
      },
      {
        index: 7,
        title: "Emotion Recognition by Edge-Weighted Hypergraph Neural Network",
        publication: "ICIP 2019",
        authors:
          "Jingzhi Shao, Junjie Zhu, Yuxuan Wei, Yifan Feng and Xibin Zhao*",
        url_pdf: "https://ieeexplore.ieee.org/abstract/document/8803207/",
        url_code: "",
        bib_tex: "publication/2019-emotion/cite.bib",
        fw_path: "publication/2019-emotion/fw.png",
      },
      {
        index: 8,
        title:
          "Physiological Signals-based Emotion Recognition via High-order Correlation Learning",
        publication: "TOMM 2019",
        authors: "Junjie Zhu, Yuxuan Wei, Yifan Feng, Xibin Zhao and Yue Gao*",
        url_pdf: "https://dl.acm.org/doi/abs/10.1145/3332374",
        url_code: "",
        bib_tex: "publication/2019-physiological/cite.bib",
        fw_path: "publication/2019-physiological/fw.png",
      },
      {
        index: 9,
        title: "Dual Channel Hypergraph Collaborative Filtering",
        publication: "KDD 2020",
        authors:
          "Shuyi Ji, Yifan Feng, Rongrong Ji, Xibin Zhao, Wanwan Tang and Yue Gao*",
        url_pdf: "https://dl.acm.org/doi/10.1145/3394486.3403253",
        url_code: "",
        bib_tex: "publication/2020-dhcf/cite.bib",
        fw_path: "publication/2020-dhcf/fw.png",
      },
      {
        index: 10,
        title: "HGNN+: General Hypergraph Neural Networks",
        publication: "IEEE T-PAMI 2022",
        authors: "Yue Gao, Yifan Feng, Shuyi Ji and Rongrong Ji*",
        url_pdf: "https://ieeexplore.ieee.org/document/9795251",
        url_code: "https://deephypergraph.readthedocs.io/en/latest/generated/dhg.models.HGNNP.html",
        bib_tex: "publication/2022-hgnnp/cite.bib",
        fw_path: "publication/2022-hgnnp/fw.png",
      },
      {
        index: 11,
        title: "SHREC'22 Track: Open-Set 3D Object Retrieval",
        publication: "Computers & Graphics 2022",
        authors: "Yifan Feng, Yue Gao* and Xibin Zhao, et al.",
        url_pdf: "https://www.sciencedirect.com/science/article/abs/pii/S0097849322001443",
        url_code: "https://github.com/yifanfeng97/multi-modal-generation-for-shrec22",
        bib_tex: "publication/2022-shrec22/cite.bib",
        fw_path: "publication/2022-shrec22/fw.png",
      },
      {
        index: 12,
        title:
          "Generating Hypergraph-Based High-Order Representations of Whole-Slide Histopathological Images for Survival Prediction",
        publication: "IEEE T-PAMI 2022",
        authors:
          "Donglin Di, Changqing Zou, Yifan Feng, Hanyan Zhou, Rongrong Ji, Qionghai Dai and Yue Gao*",
        url_pdf: "https://ieeexplore.ieee.org/document/9903546",
        url_code: "",
        bib_tex: "publication/2022-hgsurvnet/cite.bib",
        fw_path: "publication/2022-hgsurvnet/fw.png",
      },
      {
        index: 13,
        title:
          "Hierarchical Set-to-set Representation for 3D Cross-modal Retrieval",
        publication: "IEEE TNNLS 2023",
        authors: "Yu Jiang, Cong Hua, Yifan Feng and Yue Gao*",
        url_pdf: "https://ieeexplore.ieee.org/document/10316653",
        url_code: "",
        bib_tex: "publication/2023-hsr/cite.bib",
        fw_path: "publication/2023-hsr/fw.png",
      },
      {
        index: 14,
        title:
          "Hypergraph-Based Multi-Modal Representation for Open-Set 3D Object Retrieval",
        publication: "IEEE T-PAMI 2023",
        authors: "Yifan Feng, Shuyi Ji, Yu-Shen Liu and Yue Gao*.",
        url_pdf: "https://ieeexplore.ieee.org/document/10319392",
        url_code: "https://github.com/iMoonLab/HGM2R",
        bib_tex: "publication/2023-sdm2r/cite.bib",
        fw_path: "publication/2023-sdm2r/fw.png",
      },
      {
        index: 15,
        title:
          "Hypergraph Isomorphism Computation",
        publication: "IEEE T-PAMI 2024",
        authors: "Yifan Feng, Jiashu Han, Shihui Ying and Yue Gao*",
        url_pdf: "https://ieeexplore.ieee.org/abstract/document/10398457",
        url_code: "https://github.com/iMoonLab/HIC",
        bib_tex: "publication/2024-hic/cite.bib",
        fw_path: "publication/2024-hic/fw.jpg",
      },
      {
        index: 16,
        title:
          "Hypergraph Dynamic System",
        publication: "ICLR 2024",
        authors: "Jielong Yan, Yifan Feng, Shihui Ying and Yue Gao*",
        url_pdf: "https://openreview.net/forum?id=NLbRvr840Q",
        url_code: "https://github.com/iMoonLab/HDS-ODE",
        bib_tex: "publication/2024-hode/cite.bib",
        fw_path: "publication/2024-hode/fw.jpg",
      },
      {
        index: 17,
        title:
          "LightHGNN: Distilling Hypergraph Neural Networks into MLPs for 100x Faster Inference",
        publication: "ICLR 2024",
        authors: "Yifan Feng, Yihe Luo, Shihui Ying and Yue Gao*",
        url_pdf: "https://openreview.net/forum?id=lHasEfGsXL",
        url_code: "https://github.com/iMoonLab/LightHGNN",
        bib_tex: "publication/2024-lighthgnn/cite.bib",
        fw_path: "publication/2024-lighthgnn/fw.jpg",
      },
      {
        index: 18,
        title:
          "A Bilateral-Branch Joint Learning Framework for Multiplex Bipartite Network Embedding",
        publication: "Under Review",
        authors: "Shuyi Ji, Yifan Feng and Yue Gao*, et al.",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-combi/fw.png",
      },
      {
        index: 19,
        title:
          "Cross-Modal 3D Shape Retrieval via Heterogeneous Dynamic Graph Representation",
        publication: "Under Review",
        authors: "Yue Dai, Yifan Feng and Yue Gao*, et al.",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-hdgr/fw.png",
      },
      {
        index: 20,
        title:
          "Multi-View Time-Series Hypergraph Learning for Action Recognition",
        publication: "Under Review",
        authors: "Nan Ma, Zhixuan Wu, Yifan Feng and Yue Gao*, et al.",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-mv-tshl/fw.png",
      },
      {
        index: 21,
        title:
          "Hypergraph Information Bottleneck Guided Hypergraph Structure Learning",
        publication: "Under Review",
        authors: "Zizhao Zhang, Yifan Feng, Shihui Ying and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-hib/fw.png",
      },
      {
        index: 22,
        title:
          "Multi-Modal Temporal Hypergraph Neural Network for Flotation Condition Recognition",
        publication: "Under Review",
        authors: "Zunguan Fan, Yifan Feng, Yue Gao and Kang Wang*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-fcr/fw.jpg",
      },
      {
        index: 23,
        title:
          "Hypergraph Collaborative Filtering with Attribute Inference",
        publication: "Under Review",
        authors: "Yutong Jiang, Chenggang Yan, Donglin Di, Shuyi Ji, Yifan Feng, Qiang Zhao, Min He and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-hcf/fw.jpg",
      },
      {
        index: 24,
        title:
          "Graph Classification via Hypergraph",
        publication: "Under Review",
        authors: "Qingmei Tang, Yifan Feng, Zunjie Zhu,, Shihui Ying, Chenggang Yan, Wenyu Wang and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-gch/fw.jpg",
      },
      {
        index: 25,
        title:
          "Double Degree-Guided Discrete Diffusion for Hypergraph Generation",
        publication: "Under Review",
        authors: "Tao Jin, Yifan Feng, Yuhan Gao, He Min, Lei Zhang, Chenggang Yan and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-ddhg/fw.jpg",
      },
      {
        index: 26,
        title:
          "Bayesian Hypergraph Modeling",
        publication: "Under Review",
        authors: "Shuyi Ji, Yifan Feng, Shihui Ying and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-bhm/fw.jpg",
      },
      {
        index: 27,
        title:
          "Kernelized Hypergraph Neural Networks",
        publication: "Under Review",
        authors: "Yifan Feng, Yifan Zhang, Shihui Ying, Shaoyi Du and Yue Gao*",
        url_pdf: "",
        url_code: "",
        bib_tex: "",
        fw_path: "publication/2024-khgnn/fw.jpg",
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
