<template>
  <div class="container mt-5">
    <h5>Página para hacer las pruebas de eventos con vuex</h5>
    <hr />
    <div class="row mt-5 mb-5">
      <div class="col-lg-3">
        <input-comp-vuex :placeholder="placeholder"></input-comp-vuex>
      </div>
      <div class="col-lg-6">
        <count-comp-vuex></count-comp-vuex>
      </div>
    </div>

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
  </div>
</template>

<script>
import InputCompVuex from '@/components/events/InputCompVuex.vue' // Importo al componente button
import CountCompVuex from '@/components/events/CountCompVuex.vue' // Importo al componente button

export default {
  components: {
    InputCompVuex,
    CountCompVuex
  },

  data() {
    return {
      placeholder: 'Introduce tus datos'
    }
  },

  computed: {
    notes() {
      return this.$store.getters.getNotes
    },
    timestamps() {
      return this.$store.getters.getTimestamps
    }
  }
}
</script>

<style lang="scss" scoped></style>
