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
      <v-icon size="16px">
        far fa-envelope
      </v-icon>
      <span style="padding-left:6px;">lixuan.xyz@gmail.com</span>


        <span style="padding: 0 20px 0 20px;">|</span>


        <v-icon size="16px">
          fas fa-shield-alt
        </v-icon>
        <span style="padding-left:6px;"><a href="https://beian.miit.gov.cn/" target="_blank">冀ICP备11017610号-2</a></span>

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
