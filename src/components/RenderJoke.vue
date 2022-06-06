
<template>
<!-- Cada vez que la variable 'joke' sea actualizando, el valor de la misma sera rendereado en la vista -->
  <div id="joke"> 
      <h2>Joke</h2>
      <div class="renderedJoke">{{joke}}</div>
      <!-- Al clicar en el boton, llamamos a la funcion 'getJoke' -->
      <button v-on:click="getJoke()">click</button>
    </div>
</template>

<script>
    import axios from "axios"

  export default {
    name: 'RenderJoke',
    data(){
      return {
        joke: ''//variable `joke` que sera rendereada en la vista
      }
    },
    methods: {
        getJoke: async function(){//esta funcion la usaremos para recuperar los datos de la api
            let response = await axios.get('https://api.chucknorris.io/jokes/random');
            this.joke = response.data.value;
        }
    },
    mounted() {//la funcion mounted se ejecuta al acabar de rendear el componente
        this.getJoke();
    }

  }

</script>
<style>



</style>
