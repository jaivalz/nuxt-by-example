<template>
  <div class="container mt-5">
    <p>
      Hola chato, esto es para los eventos, <br />en estos ejemplos he usado el
      Eventbus, pero con lo que he buscado en internet lo que se utiliza es
      this.$bus.$emit... <br />
      Lo siguiente sera con vuex
    </p>
    <hr />

    <input-comp :placeholder="placeholder"></input-comp>

    <div class="row mt-5 mb-5">
      <div class="col-lg-6">
        <h4>Notes</h4>
        <div v-for="(note, index) in notes" :key="index">
          {{ note }}
        </div>
      </div>
      <div class="col-lg-6">
        <h4>Timestamps</h4>
        <div v-for="(timestamp, index) in timestamps" :key="index">
          {{ timestamp }}
        </div>
      </div>
    </div>
    <count-comp></count-comp>
  </div>
</template>
<script>
import InputComp from '@/components/events/InputComp.vue' // Importo al componente button
import CountComp from '@/components/events/CountComp.vue' // Importo al componente button

export default {
  components: {
    InputComp,
    CountComp
  },

  data() {
    return {
      notes: [],
      timestamps: [],
      placeholder: 'Escribe aqui'
    }
  },

  created() {
    this.$bus.$on('add-note', event => this.addNote(event))
  },

  methods: {
    addNote(event) {
      this.notes.push(event.note)
      this.timestamps.push(event.timestamp)
    }
  }
}
</script>
<style scoped></style>
