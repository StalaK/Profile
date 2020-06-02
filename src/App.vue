<template>
  <div id="app">
    <Layout>
      <router-view />
    </Layout>
  </div>
</template>

<script>
  import Layout from '@/components/Layout'

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
