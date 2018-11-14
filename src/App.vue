<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'App'
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* text-align: center;
     color: #2c3e50;
     margin-top: 60px;*/
    height: 100%;
  }

  /*css 初始化*/
  html, body, div, span, object, iframe, h1, h2,
  h3, h4, h5, h6, p, blockquote, pre, abbr, address, cite, code, del, dfn,
  em, img, ins, kbd, q, samp, small, strong, sub, sup, var, b, i, dl, dt, dd,
  ol, ul, li, fieldset, form, label, legend, table, caption, tbody,
  tfoot, thead, tr, th, td, article, aside, canvas, details, figcaption,
  figure, footer, header, hgroup, menu, nav, section, summary, time, mark,
  audio, video {
    margin: 0;
    padding: 0;
    border: 0;
    outline: 0;
    font-size: 100%;
    vertical-align: baseline;
    background: transparent;
    outline-style: none; /*FF*/
    box-sizing: border-box;
    list-style: none;
  }

  body, html {
    height: 100%;
    /*min-width: 1140px*/
  }

  a {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    vertical-align: baseline;
    background: transparent;
    text-decoration: none;
    out-line: none;
    color: #333;
  }

  a:hover, a:focus {
    text-decoration: none;
    bblr: expression(this.onFocus=this.blur()); /*IE*/
    outline-style: none; /*FF*/
  }

  table {
    border-collapse: collapse;
    border-spacing: 0;
  }

  input, select {
    vertical-align: middle;
  }


</style>
