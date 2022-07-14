<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">News</p>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-timeline dense class="text-h6 font-weight-regular">
          <v-timeline-item small fill-dot>
            <v-row dense no-gutters>
              <v-col
                md="2"
                cols="12"
                class="grey--text text--darken-2 font-weight-medium font-italic"
              >
                Jul. 2022.</v-col
              >
              <v-col md="10" cols="12" class="align-self-center">
                One paper has been accepted by Computers & Graphics 2022.
              </v-col>
            </v-row>
          </v-timeline-item>
          <v-timeline-item small fill-dot>
            <v-row dense no-gutters>
              <v-col
                md="2"
                cols="12"
                class="grey--text text--darken-2 font-weight-medium font-italic"
              >
                Jun. 2022.</v-col
              >
              <v-col md="10" cols="12" class="align-self-center">
                I have developed an online multi-modal 3D object retrieval
                system. Welcome to
                <a href="https://moon-lab.tech/vors" target="_blank">play</a>.
              </v-col>
            </v-row>
          </v-timeline-item>
          <v-timeline-item small fill-dot>
            <v-row dense no-gutters>
              <v-col
                md="2"
                cols="12"
                class="grey--text text--darken-2 font-weight-medium font-italic"
              >
                May. 2022.</v-col
              >
              <v-col md="10" cols="12" class="align-self-center">
                One paper has been accpted by IEEE T-PAMI 2022.
              </v-col>
            </v-row>
          </v-timeline-item>
          <v-timeline-item small fill-dot>
            <v-row dense no-gutters>
              <v-col
                md="2"
                cols="12"
                class="grey--text text--darken-2 font-weight-medium font-italic"
              >
                Feb. 2022.</v-col
              >
              <v-col md="10" cols="12" class="align-self-center">
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
