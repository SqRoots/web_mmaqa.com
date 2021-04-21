<template>
  <v-footer
    app
    height="auto"
    :inset="true"
  >
    <v-card
      class="flex"
      flat
      color="#dedcd4"
      style="border-top: 1px solid rgba(0,0,0,0.1);"
    >

      <!-- about me -->
      <v-card-actions
        class="justify-center brown--text"
        style="background-color:#ceccc4;"
      >
        <v-tooltip top>
          <template v-slot:activator="{ on }">
            <v-btn
              slot="activator"
              class="mx-3 brown--text"
              icon
              target="_blank"
              v-on="on"
            >
              <v-icon size="16px">
                far fa-envelope
              </v-icon>
            </v-btn>
          </template>
          <span>lixuan.xyz@gmail.com</span>
        </v-tooltip>


        <span>&nbsp;</span>


        <v-tooltip top>
          <template v-slot:activator="{ on }">
            <v-btn
              slot="activator"
              class="mx-3 brown--text"
              icon
              href="https://beian.miit.gov.cn/"
              target="_blank"
              v-on="on"
            >
              <v-icon size="16px">
                fas fa-shield-alt
              </v-icon>
            </v-btn>
          </template>
          <span>冀ICP备11017610号-2</span>
        </v-tooltip>

      </v-card-actions>
    </v-card>
  </v-footer>
</template>

<script>
// const axios = require('axios');

export default {
  name: 'Footer',
  data() {
    return {
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  footer{
    position: inherit;
    margin: 0;
    padding: 0;
  }

  .v-card {
    border-radius: 10px;
    border: 0;
    margin: 0;
    padding: 0;
  }
</style>
