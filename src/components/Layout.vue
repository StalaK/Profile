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
        <slot></slot>
      </div>
    </div>
    <div class="twitter-panel">
      <a class="twitter-timeline" data-width="500" data-height="400" data-dnt="true" data-theme="light" href="https://twitter.com/Wow_Josh?ref_src=twsrc%5Etfw">Tweets by Wow_Josh</a> 
    </div>
  </div>
</template>

<script>
  import Navbar from '@/components/Navbar'

  export default {
    components: {
      Navbar
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
    width: 10%;
  }

  .right-panel {
    display: inline-block;
    width: 60%;
    vertical-align: top;
  }

  .twitter-panel {
    margin-left: 15px;
    padding: 5px;
    display: inline-block;
    width: 25%;
    vertical-align: top;
    border: 1px solid black;
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
