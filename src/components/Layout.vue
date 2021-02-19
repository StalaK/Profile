<template>
  <b-container class="page">
    <b-row>
      <Navbar class="navbar" v-on:navigate="displayPage($event)"/>
    </b-row>
    <b-row>
      <b-col class="content-area" cols="12" lg="7">
        <slot></slot>
      </b-col>
      <b-col cols="12" lg="4">
        <b-row>
          <b-col class="content-area">
            <Profile />
          </b-col>
        </b-row>
        <b-row>
          <b-col class="content-area twitter">
              <a class="twitter-timeline" data-width="500" data-height="400" data-dnt="true" data-theme="light" 
                href="https://twitter.com/Wow_Josh?ref_src=twsrc%5Etfw">Tweets by Wow_Josh</a> 
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  import Navbar from '@/components/Navbar'
  import Profile from '@/components/Profile'
  
  export default {
    components: {
      Navbar,
      Profile
    }
  }
</script>

<style>
  .twitter {
    text-align-last: center;
  }

  .content-area {
    border: 0px;
    border-radius: 15px;
    padding: 15px;
    margin: 5px 15px 15px 0px;
    height:fit-content;
    background-color: white;
  }

  a:link {
    color: #4c7f7f !important;
  }

  a:visited {
    color: #426f6f !important;
  }

  a:hover {
    color: #2f4f4f !important;
  }
</style>
