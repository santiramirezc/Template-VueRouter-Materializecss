<template>
  <div id="app">
    <Header></Header>
    <router-view/>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'

  export default {
    mounted() {
      M.AutoInit(); // That way, it is only initialized when the component is mounted
      
      document.addEventListener('DOMContentLoaded', function() {
        var elems = document.querySelectorAll('.collapsible');
        var instances = M.Collapsible.init(elems, {});
      });
    },created(){
      let icons = document.createElement('link');    
      icons.setAttribute('href',"https://fonts.googleapis.com/icon?family=Material+Icons");
      icons.setAttribute('rel',"stylesheet");
      document.head.appendChild(icons);
    },
    components: {
      Header,
      Footer
    }
  }
</script>

<style>
  @import '/css/materialize.min.css';
</style>
