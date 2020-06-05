<template>
  <b-container class="page">
    <b-row>
      <Navbar class="navbar" v-on:navigate="displayPage($event)"/>
    </b-row>
    <b-row>
      <b-col class="content-area" cols="12" lg="8">
        <slot></slot>
      </b-col>
      <b-col class="content-area twitter" cols="12" lg="3">
        <a class="twitter-timeline" data-width="500" data-height="400" data-dnt="true" data-theme="light" 
          href="https://twitter.com/Wow_Josh?ref_src=twsrc%5Etfw">Tweets by Wow_Josh</a> 
      </b-col>
    </b-row>
  </b-container>
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
  .twitter {
    text-align-last: center;
  }

  .content-area {
    border: 1px solid black;
    padding: 15px;
    margin: 5px 10px 5px 0px;
    height:fit-content;
  }

</style>
