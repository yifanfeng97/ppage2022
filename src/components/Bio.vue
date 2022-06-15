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
          <p class="text-h5 grey--text text--darken-1" color="grey">
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
          <v-col cols="12" class="text-h3"> Biography </v-col>
          <v-col cols="12" class="text-h6 font-weight-regular">
            <p>
              I am currently a first-year Ph.D student in the
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
              >. I have received the BE degree in computer science and
              technology from
              <a
                class="text-decoration-none"
                href="http://www.xidian.edu.cn/"
                target="_blank"
                >Xidian University</a
              >
              in 2018, and the MS degree supervised by Professor
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
              Networks, and Complex Network. Now, I am developing a toolkit for
              hypergraph nerual networks, and it will be released soon. If you
              are interested in my research, please email me at
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
          <v-col md="6" cols="12">
            <p class="text-h4">Education</p>
            <v-timeline dense class="text-h6 font-weight-regular">
              <v-timeline-item small fill-dot
                >B.S. of Computer Science from Xidian University, 2014 -
                2018.</v-timeline-item
              >
              <v-timeline-item small fill-dot
                >M.S. of Intelligent Science and Technology from
                <a
                  class="text-decoration-none"
                  href="https://mac.xmu.edu.cn/"
                  target="_blank"
                  >MAC</a
                >, Xiamen University, 2018 - 2021.</v-timeline-item
              >
              <v-timeline-item small fill-dot
                >Ph.D. of School of Software from
                <a
                  class="text-decoration-none"
                  href="https://www.moon-lab.tech/"
                  target="_blank"
                  >iMoon Lab</a
                >, Tsinghua University, 2021 - Present.</v-timeline-item
              >
            </v-timeline>
          </v-col>
          <v-col md="6" cols="12">
            <p class="text-h4">Intern Experiment</p>
            <v-timeline dense class="text-h6 font-weight-regular">
              <v-timeline-item small fill-dot
                >Institute of Deep Learning, Baidu, 2017 -
                2018.</v-timeline-item
              >
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
