<template>
  <div id="app">
    <RenderJoke />
    <RenderCategories />
  </div>
</template>

<script>

  import  RenderJoke  from './components/RenderJoke.vue'
  import RenderCategories from './components/RenderCategories.vue'
  export default {
    name: 'App',
    components: {
      RenderJoke, //importamos nuestro componente 'RenderJoke', que sera rendereado en nuestro template
      RenderCategories //importamos nuestro componente 'RenderCategories'
    },
    data(){
      return {
        listJokes: []
      }
    },
    computed: {
      fullName(){
        return `${this.name} ${this.surname}`
      }
    }

  }

</script>
<style>
@import './assets/base.css';


</style>
