<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
  html,body,#app{
    width: 100%;
    /*max-width: 600px;*/
    height: 100%;
    margin: 0 auto;
  }
  #app{
    background: url("./static/img/bg.jpg") repeat;
    background-size: 50%;
  }
  *{
    margin: 0;
    padding: 0;
  }
</style>
