<template>
  <div class="page">
    <div class="title">
      <h1>Josh Hughes</h1>
    </div>
    <div class="left-panel">
      <Navbar class="navbar" />
    </div>
    <div class="right-panel">
      <div class="content-area">
        <ol>
          Todo:
          <li>Listen to event emitted by navbar component. Load new page content from event here.</li>
          <li>Styling</li>
          <li>Add pages</li> 
        </ol>
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from './components/Navbar'

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
