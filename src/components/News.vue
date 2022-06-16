<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">News</p>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-timeline dense class="text-h6 font-weight-regular">
          <v-timeline-item small fill-dot>
            <v-row>
              <v-col md="2" cols="12"> May. 2022.</v-col>
              <v-col md="10" cols="12">
                One paper has been accpted by IEEE T-PAMI.
              </v-col>
            </v-row>
          </v-timeline-item>
          <v-timeline-item small fill-dot>
            <v-row>
              <v-col md="2" cols="12"> Feb. 2022.</v-col>
              <v-col md="10" cols="12">
                We organize a track "<a
                  class="text-decoration-none"
                  href="https://www.moon-lab.tech/shrec22"
                  target="_blank"
                  >Open-Set 3D Object Retrieval</a
                >" in SHREC'22.
              </v-col>
            </v-row>
          </v-timeline-item>
        </v-timeline>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyNews",

  data: () => ({}),
};
</script>
