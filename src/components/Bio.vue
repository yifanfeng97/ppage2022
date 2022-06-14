<template>
  <v-container class="mt-6">
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
            Ph.D of School of Software
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
      </v-col>
      <v-col md="8" cols="12"> This is ME! </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyBio",

  data: () => ({}),
};
</script>
