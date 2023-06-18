<script>
//Opcion 1 para mandar la variable al html
/*
export default{
  data(){
    return {
      //Mando esto al template en el h2 de contador
      contador: 200
    };
  }
};
*/

//Opcion 2
export default{
  data: () =>({
    contador: 10,
  }),
  methods:{
    incrementar(){
      this.contador++;
      //this porque si no aparece como "undefined"
      //entonces debo indicarle que esta dentro del contexto actual
    },
    disminuir(){
      this.contador--;
    },
    reiniciar(){
      this.contador = 10;
    }
  }
};
</script>


<template>

  <div class="container">
    <img src="./assets/logo.svg" alt="logo vue" width="125" height="125"/>
    <small>
      <h1>Hola mundo desde Vue.js 3</h1>  
    </small>
    

    <hr>

    <h2>Contador: {{ contador }}</h2>
    <!--
      v-on:click="saludar()"
      v-> Directiva vue
      on->llamarMetodos/eventos
      :NombreTipoMetodo/funciones
      "nombreFuncion"

      @ puede usarse en vez de v-on:
    -->
    <button @click="incrementar()" >+1</button>
    <button @click="disminuir()">-1</button>
    <button @click="reiniciar()">Reset</button>
  </div>

  <!--Si saco una etiqueta html fuera de la template truena la aplicacion-->
</template>

<!--scoped me permite que los estilos aplicados aquí sean locales, no globales-->
<style scoped>

.container{
  text-align: center;
}

small{
  color: #666;
}

h2{
  font-size: 2rem;
}

button{
  cursor: pointer;
  font-size: 1.5rem;
  margin: 0px 6px;
}
/* 
h1{
  color: rgb(0, 97, 0)
}
*/
</style>