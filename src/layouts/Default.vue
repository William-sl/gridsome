<template>
  <div class="layout">
    <header class="header">
      <img @click="this.$router.replace('/')" width="50px" height="50px" src="https://gridsome-forestry.netlify.app/assets/img/logo.332701b7.svg"/>
      <nav class="nav">
        <g-link class="nav__link" to="/">Journal</g-link>
        <g-link class="nav__link" to="/about/">Say Hi</g-link>
      </nav>
    </header>
    <div style="padding-top:80px">
      <slot/>
    </div>
    <footer>
      <div class="footer-title">
        LATEST AND GERATEST
      </div>
      <div class="footer-content">
        <div>Gridsome with Forestry</div>
        <div>VueJS for your next project</div>
        <div>macOS development environment</div>
        <div>About Typography</div>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}
.footer-title{
    display: block;
    font-weight: 700;
    margin-bottom: .5rem;
    font-size: .6rem;
}
.footer-content{
  max-width: 100%;
  margin: 0 2rem;
  border: 1px solid gray;
  display: flex;
}
.footer-content div{
    display: block;
    padding: 2rem;
    transition: background .25s ease;
    text-decoration: none;
    border-right: 1px solid gray;
}
.footer-content div:nth-child(4){
  border-right: none;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  position: relative;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
  position: fixed;
  top: 0;
  width: 680px;
  z-index: 999;
  
}
footer{
  margin-top: 20px;
}

.nav__link {
  margin-left: 20px;
}
</style>
