<template>
  <v-footer color="primary" dark padless>
    <v-container fluid class="pa-0">
      <v-row class="align-center" no-gutters>
        <v-col cols="12">
          <v-card-subtitle class="text-center pb-1 text-subtitle-1">
            <strong>Yifan Feng</strong>
          </v-card-subtitle>
          <v-card-text class="text-center">
            Copyright © 2022 -
            {{ new Date().getFullYear() }}, All rights reserved.
          </v-card-text>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script>
export default {
  name: "MyFooter",
};
</script>
