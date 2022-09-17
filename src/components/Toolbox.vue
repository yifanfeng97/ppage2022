<template>
  <v-container>
    <v-row>
      <v-col cols="12"><p class="text-h4">Released Toolbox</p></v-col>
    </v-row>
    <v-row class="text-body-1">
      <v-col cols="12" class="text-h6">
        <a
          class="text-decoration-none"
          href="http://deephypergraph.com/"
          target="_blank"
          >DeepHypergraph</a
        ></v-col
      >
      <!-- <v-col cols="12" class="d-flex justify-start"> -->
      <v-col cols="12" class="d-inline-flex">
        <a
          v-for="item in tags"
          :key="item.idx"
          :href="item.link"
          target="_blank"
        >
          <v-img class="mr-2" :src="item.icon" max-height="20px" contain />
        </a>
        <!-- <a href="http://deephypergraph.com/" target="_blank">
          <v-img
            class="mr-2"
            src="https://github.com/yifanfeng97/dhg-page-source/actions/workflows/website.yml/badge.svg"
            max-height="20px"
            contain
          />
        </a>
        <a href="https://pypi.org/project/dhg/" target="_blank">
          <v-img
            class="mr-2"
            src="https://img.shields.io/pypi/v/dhg?color=purple"
          />
        </a>
        <a
          href="https://deephypergraph.readthedocs.io/en/latest/?badge=latest"
          target="_blank"
        >
          <v-img
            class="mr-2"
            src="https://readthedocs.org/projects/deephypergraph/badge/?version=latest"
          />
        </a>
        <a href="https://pypistats.org/packages/dhg" target="_blank">
          <v-img class="mr-2" src="https://img.shields.io/pypi/dm/dhg.svg" />
        </a>
        <a
          href="https://github.com/iMoonLab/DeepHypergraph/blob/main/LICENSE"
          target="_blank"
        >
          <v-img
            class="mr-2"
            src="https://img.shields.io/github/license/imoonlab/DeepHypergraph"
          />
        </a> -->
      </v-col>
      <v-col cols="12" class="d-flex justify-center">
        <!-- <v-img
          src="../assets/logo_DHG.png"
          max-height="200"
          contain
        ></v-img> -->
        <video loop muted autoplay playsinline width="100%" :src="video_src">
          <p>Your browser does not support the video tag.</p>
        </video>
      </v-col>
      <v-col>
        <p>
          <a
            class="text-decoration-none"
            href="http://deephypergraph.com/"
            target="_blank"
            >Homepage</a
          >
          |
          <a
            class="text-decoration-none"
            href="https://github.com/iMoonLab/DeepHypergraph"
            target="_blank"
            >Github</a
          >
          |
          <a
            class="text-decoration-none"
            href="https://deephypergraph.readthedocs.io/"
            target="_blank"
            >Documentation</a
          >
          |
          <a
            class="text-decoration-none"
            href="https://deephypergraph.readthedocs.io/en/latest/zh/overview.html"
            target="_blank"
            >中文文档</a
          >
        </p>
        <p>
          DHG (DeepHypergraph) is a deep learning library built upon
          <a
            class="text-decoration-none"
            href="https://github.com/iMoonLab/DeepHypergraph"
            target="_blank"
            >PyTorch</a
          >
          for learning with both Graph Neural Networks and Hypergraph Neural
          Networks. It is a general framework that supports both low-order and
          high-order message passing like
          <strong>
            from vertex to vertex, from vertex in one domain to vertex in
            another domain, from vertex to hyperedge, from hyperedge to vertex,
            from vertex set to vertex set.</strong
          >
        </p>
        <p>
          It supports a wide variety of structures like low-order structures
          (simple graph, directed graph, bipartite graph, etc.), high-order
          structures (simple hypergraph, etc.). Various spectral-based
          operations (like Laplacian-based smoothing) and spatial-based
          operations (like message psssing from domain to domain) are integrated
          inside different structures. It provides multiple common metrics for
          performance evaluation on different tasks. Many state-of-the-art
          models are implemented and can be easily used for research. We also
          provide various visualization tools for both low-order structures and
          high-order structures.
        </p>
        <p>
          In addition, DHG's
          <a
            class="text-decoration-none"
            href="https://deephypergraph.readthedocs.io/en/latest/api/experiments.html"
            target="_blank"
            >dhg.experiments</a
          >
          module (that implements <strong>Auto-ML</strong> upon
          <a
            class="text-decoration-none"
            href="https://optuna.org/"
            target="_blank"
            >Optuna</a
          >) can help you automatically tune the hyper-parameters of your models
          in training and easily outperforms the state-of-the-art models.
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyToolbox",
  computed: {
    video_src() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return require("../assets/neuron_actions_4s_v1_text.mp4");
        case "sm":
          return require("../assets/neuron_actions_4s_v1_text.mp4");
        case "md":
          return require("../assets/neuron_actions_4s_v1_wide_text.mp4");
        case "lg":
          return require("../assets/neuron_actions_4s_v1_wide_text.mp4");
        case "xl":
          return require("../assets/neuron_actions_4s_v1_wide_text.mp4");
        default:
          return require("../assets/neuron_actions_4s_v1_wide_text.mp4");
      }
    },
  },
  data: () => ({
    tags: [
      {
        idx: 1,
        link: "http://deephypergraph.com/",
        icon: "https://github.com/yifanfeng97/dhg-page-source/actions/workflows/website.yml/badge.svg",
      },
      {
        idx: 2,
        link: "https://pypi.org/project/dhg/",
        icon: "https://img.shields.io/pypi/v/dhg?color=purple",
      },
      // {
      //   idx: 3,
      //   link: "https://pypi.org/project/dhg/",
      //   icon: "https://img.shields.io/pypi/pyversions/dhg",
      // },
      {
        idx: 4,
        link: "https://deephypergraph.readthedocs.io/en/latest/?badge=latest",
        icon: "https://readthedocs.org/projects/deephypergraph/badge/?version=latest",
      },
      {
        idx: 5,
        link: "https://pypistats.org/packages/dhg",
        icon: "https://img.shields.io/pypi/dm/dhg.svg",
      },
      // {
      //   idx: 6,
      //   link: "https://github.com/iMoonLab/DeepHypergraph/blob/main/LICENSE",
      //   icon: "https://img.shields.io/github/license/imoonlab/DeepHypergraph",
      // },
    ],
  }),
};
</script>
