<template>
  <b-container id="app" fluid>
    <Layout>
      <transition name="fade" mode="out-in">
        <router-view />
      </transition>
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

  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }

  .fade-leave-active {
    transition: opacity .5s;
  }
  
  .fade-enter, .fade-leave-to  {
    opacity: 0;
  }

</style>
