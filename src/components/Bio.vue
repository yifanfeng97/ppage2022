<template>
  <v-container>
    <v-row>
      <v-col md="4" cols="12">
        <v-col cols="12" class="d-flex justify-center">
          <v-card max-width="400" width="400">
            <v-img src="../assets/fengyifan.jpg" :aspect-ratio="8 / 7"> </v-img>
          </v-card>
        </v-col>
        <v-col cols="12" class="text-center">
          <p class="text-h4">丰一帆 (Yifan Feng)</p>
          <p class="text-h5 grey--text text--darken-1">
            Ph.D. of School of Software
          </p>
          <p class="text-h6">
            <a
              class="text-decoration-none"
              href="https://www.tsinghua.edu.cn/"
              target="_blank"
              >Tsinghua University</a
            >
          </p>
        </v-col>
        <v-col cols="12" class="d-flex justify-center">
          <v-btn
            class="mx-4"
            href="https://scholar.google.com.hk/citations?user=WntYF-sAAAAJ&hl=zh-CN"
            icon
          >
            <v-icon large> mdi-school </v-icon>
          </v-btn>
          <v-btn class="mx-4" href="https://github.com/yifanfeng97/" icon>
            <v-icon large> mdi-github </v-icon>
          </v-btn>
          <v-btn class="mx-4" href="mailto:evanfeng97@qq.com" icon>
            <v-icon large> mdi-email </v-icon>
          </v-btn>
        </v-col>
      </v-col>
      <v-col md="8" cols="12">
        <v-row>
          <v-col cols="12" class="text-h4"> Biography </v-col>
          <v-col cols="12" class="text-h6 font-weight-regular">
            <p>
              I am currently a first-year Ph.D. student in the
              <a
                class="text-decoration-none"
                href="https://www.thss.tsinghua.edu.cn/"
                target="_blank"
                >School of Software</a
              >
              at
              <a
                class="text-decoration-none"
                href="https://www.tsinghua.edu.cn/"
                target="_blank"
                >Tsinghua University</a
              >. My Ph.D supervisor is Associate Professor
              <a
                class="text-decoration-none"
                href="https://www.moon-lab.tech/"
                target="_blank"
                >Yue Gao</a
              >. I have received the B.E. degree in computer science and
              technology from
              <a
                class="text-decoration-none"
                href="http://www.xidian.edu.cn/"
                target="_blank"
                >Xidian University</a
              >
              in 2018, and the M.S. degree in intelligent science and technology
              supervised by Professor
              <a
                class="text-decoration-none"
                href="https://mac.xmu.edu.cn/"
                target="_blank"
                >Rongrong Ji</a
              >
              from
              <a
                class="text-decoration-none"
                href="https://www.xmu.edu.cn/"
                target="_blank"
                >Xiamen University</a
              >
              in 2021. My research interests include 3D Object Recognition, 3D
              Object Retrieval, Open-set 3D Object Retrieval, Hypergraph Neural
              Networks, and Complex Network. I have released the
              <a
                class="text-decoration-none"
                href="http://deephypergraph.com/"
                target="_blank"
                >DeepHypergraph (DHG)</a
              >
              toolkit for Learning with Graph Neural Networks and Hypergraph
              Neural Networks. If you are interested in my research, please
              email me at
              <a class="text-decoration-none" href="mailto:evanfeng97@gmail.com"
                >evanfeng97@gmail.com</a
              >
              or
              <a class="text-decoration-none" href="mailto:evanfeng97@qq.com"
                >evanfeng97@qq.com</a
              >.
            </p>
          </v-col>
        </v-row>
        <v-row>
          <v-col md="12" cols="12">
            <p class="text-h5">Experiments</p>
            <v-timeline dense class="text-body1 font-weight-regular">
              <v-timeline-item small fill-dot>
                <v-row dense no-gutters>
                  <v-col
                    md="2"
                    cols="12"
                    class="grey--text text--darken-2 font-weight-medium font-italic"
                    >2014 - 2018</v-col
                  >
                  <v-col
                    md="10"
                    cols="12"
                    class="align-self-center text-body-1"
                  >
                    B.E. in Computer Science, Xidian University.
                  </v-col>
                </v-row>
              </v-timeline-item>
              <v-timeline-item small fill-dot>
                <v-row dense no-gutters>
                  <v-col
                    md="2"
                    cols="12"
                    class="grey--text text--darken-2 font-weight-medium font-italic"
                    >2017 - 2018</v-col
                  >
                  <v-col
                    md="10"
                    cols="12"
                    class="align-self-center text-body-1"
                  >
                    Intern in Institute of Deep Learning, Baidu Inc.
                  </v-col>
                </v-row>
              </v-timeline-item>
              <v-timeline-item small fill-dot>
                <v-row dense no-gutters>
                  <v-col
                    md="2"
                    cols="12"
                    class="grey--text text--darken-2 font-weight-medium font-italic"
                    >2018 - 2021</v-col
                  >
                  <v-col md="10" cols="12" class="align-self-center text-body-1"
                    >M.S. in Intelligent Science and Technology from
                    <a
                      class="text-decoration-none"
                      href="https://mac.xmu.edu.cn/"
                      target="_blank"
                      >MAC</a
                    >, Xiamen University.
                  </v-col>
                </v-row>
              </v-timeline-item>
              <v-timeline-item small fill-dot>
                <v-row dense no-gutters>
                  <v-col
                    md="2"
                    cols="12"
                    class="grey--text text--darken-2 font-weight-medium font-italic"
                    >2021 - Now</v-col
                  >
                  <v-col md="10" cols="12" class="align-self-center text-body-1"
                    >Ph.D. of School of Software from
                    <a
                      class="text-decoration-none"
                      href="https://www.moon-lab.tech/"
                      target="_blank"
                      >iMoon Lab</a
                    >, Tsinghua University.
                  </v-col>
                </v-row>
              </v-timeline-item>
            </v-timeline>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyBio",

  data: () => ({}),
};
</script>
