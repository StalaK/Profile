<template>
  <div class="page">
    <div class="title">
      <h1>Josh Hughes</h1>
    </div>
    <div class="left-panel">
      <Navbar class="navbar" v-on:navigate="displayPage($event)"/>
    </div>
    <div class="right-panel">
      <div class="content-area">
        <Home v-if="displayedPage == 'home'" />
        <About v-if="displayedPage == 'about'" />
        <Portfolio v-if="displayedPage == 'portfolio'" />
        <Contact v-if="displayedPage == 'contact'" />
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from './components/Navbar'
  import About from './components/About'
  import Contact from './components/Contact'
  import Home from './components/Home'
  import Portfolio from './components/Portfolio'

  export default {
    components: {
      Navbar,
      About,
      Contact,
      Home,
      Portfolio
    },
    data () { 
      return {
        displayedPage: 'home'
      }
    },
    methods: {
      displayPage: function (page) {
        this.displayedPage = page;
      }
    }
  }
</script>

<style>
  .page {
    margin-left: 20%;
    margin-right: 20%;
  }

  .left-panel {
    display: inline-block;
    width: 20%;
  }

  .right-panel {
    display: inline-block;
    width: 75%;
    vertical-align: top;
  }

  .content-area {
    border: 1px solid black;
    padding: 15px;
    margin-left: 20px;
  }

  .navbar {
    border: 1px solid black;
    padding: 10px 10px 10px 20px;
  }

</style>
