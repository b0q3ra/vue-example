
<template>
<!-- Cada vez que la variable 'joke' sea actualizando, el valor de la misma sera rendereado en la vista -->
  <div id="categories"> 
      <h2>Categories</h2>
      <ul>
          <li v-for="category in categories">
            {{category}}
          </li>
    </ul>
  </div>
</template>

<script>
    import axios from "axios"

  export default {
    name: 'RenderCategories',
    data(){
      return {
        categories: []//variable `joke` que sera rendereada en la vista
      }
    },
    methods: {
        getCategories: async function(){
            let response = await axios.get('https://api.chucknorris.io/jokes/categories');
            this.categories = response.data;
        }
    },
    mounted() {//se ejecuta al acabar de renderear el componente

        this.getCategories()//ejecuta la funcion getCategories

    }

  }

</script>
<style>



</style>
