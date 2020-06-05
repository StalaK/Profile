<template>
  <b-container id="app" fluid>
    <Layout>
      <router-view />
    </Layout>
  </b-container>
</template>

<script>
  import Layout from '@/components/Layout'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  export default {
    components: {
      Layout,
    },
    mounted: function () {
      let twitterScript = document.createElement('script');
      twitterScript.setAttribute('src', 'https://platform.twitter.com/widgets.js');
      document.head.appendChild(twitterScript);
    }
  }
</script>

<style>
</style>
