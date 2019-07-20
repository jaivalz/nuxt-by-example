// Voy a crear un componente button para ponerselo a la página de un único
personaje

<template>
  <div>
    <b-card
      :title="'Hola' + ' ' + form.title"
      :img-src="cardImg"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-8"
    >
      <slot> </slot>
      <b-card-text class="small">
        <input v-model="form.title" placeholder="¿Como te llamas?" />
        <br />
        <br />
        <h1 v-if="form.title === 'Juan'">
          <slot name="respuesta">Funciona!</slot>
          <img
            src="data:image/jpeg;base64,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"
            fluid
            alt=""
          />
        </h1>

        <h2 v-else>
          <slot name="pregunta">UwU</slot>
        </h2>
        <br />
        <b-button variant="danger" @click="onReset"
          >No soy {{ form.title }}</b-button
        >
      </b-card-text>
    </b-card>
  </div>
</template>

<script>
export default {
  // Defino los props del button (prop = atributo), en este caso tengo type (success/warning/danger...) y size (big/medium/small...)
  props: {
    title: {
      type: String,
      default: ''
    },
    imgSrc: {
      type: String,
      default: ''
    },
    imgAlt: {
      type: String,
      default: ''
    }
  },

  data() {
    return {
      form: {
        title: ''
      }
    }
  },

  computed: {
    cardImg() {
      return this.imgSrc
    }
  },

  methods: {
    onReset() {
      this.form.title = ''
    }
  }
  // Con el computed puedo cambiar el valor del componente, en este caso al cambiar this.type y this.size estoy cambiando el type y size del button
}
</script>

<style scoped>
/* Estilo general del componente */

.jv-button {
  background-color: blue;
  color: white;
  border: 0;
  border-radius: 2px;
  padding: 0 20px;
  margin: 25px;
  cursor: pointer;
}

/* Estilos dependiendo del type y size del componente, esto se ha utilizado siguiendo la metodología bem: http://getbem.com/ */

.jv-button--success {
  background-color: green;
}
.jv-button--warning {
  background-color: orange;
}
.jv-button--danger {
  background-color: red;
}
.jv-button--big {
  font-size: 18px;
}
.jv-button--medium {
  font-size: 18px;
}
.jv-button--small {
  font-size: 18px;
}
.jv-button--mini {
  font-size: 18px;
}
</style>
