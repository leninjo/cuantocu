<template>
  <div class="container my-5">
    <div class="columns is-mobile py-5">
      <div class="column is-12-mobile is-half-desktop is-offset-one-quarter">
        <h3 class="title is-size-4 has-text-centered ">¿Cuánto cada uno?</h3>
        <hr>
          <b-field label="Total a pagar">
              <b-numberinput v-model="cantidad" min="1" controls-position="compact"></b-numberinput>
          </b-field>
          <b-field label="Cantidad de personas">
              <b-numberinput v-model="personas" min="1" controls-position="compact"></b-numberinput>
          </b-field>
        <p class="subtitle is-size-4 has-text-centered ">Cantidad por persona <strong class="subtitle is-size-3">{{ total }}</strong></p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      cantidad: 100,
      personas: 1
    }
  },
  computed: {
    total(){
      if (this.cantidad == 0 && this.personas == 0){
        return 0;
      }
      return this.cantidad / this.personas;
    }
  },
  methods:{
    incrementCantidad(){
      this.cantidad++;
    },
    incrementPersonas(){
      this.personas++;
    },
    decrementCantidad(){
      this.cantidad--;
    },
    decrementPersonas(){
      this.personas--;
    },
    tablePersonas(){
      
    }
  }
}
</script>