<template>
  <div>
    <div><h3>Componente lista y tabla sana</h3></div>
    <h4>1.- Tabla sin ordenar</h4>
    <div>
      <p class="mt-3">Current Page: {{ currentPage }}</p>
      <b-table
        id="my-table"
        :items="edadGente(genteGuay)"
        :per-page="perPage"
        :current-page="currentPage"
        small
      ></b-table>
      <b-pagination
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        aria-controls="my-table"
      ></b-pagination>
      <hr />
      <h4>2.- Tabla ordenada</h4>
      <b-table
        id="tabla-sana"
        striped
        hover
        :items="genteGuay"
        :fields="fields"
        :per-page="perPage"
        :current-page="currentPage"
      ></b-table>
      <b-pagination
        v-model="currentPage"
        :total-rows="rows"
        :per-page="perPage"
        aria-controls="tabla-sana"
      ></b-pagination>
      <hr />
      <div v-for="(persona, index) in genteGuay" :key="index">
        {{ persona.nombre }} / {{ persona.edad }}
        <br />
        <b-button variant="sm info" @click="persona.edad++"
          >Sumale 1 año</b-button
        >
      </div>
      ----
      <hr />
      <p>Ordenado por edad</p>
      <div v-for="(persona, index) in edadGente(genteGuay)" :key="index">
        {{ persona.nombre }} tiene {{ persona.edad }} años
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      perPage: 4,
      currentPage: 1,
      fields: [
        {
          key: 'id',
          sortable: true
        },
        {
          key: 'nombre',
          sortable: false
        },
        {
          key: 'edad',
          sortable: true
          // Variant applies to the whole column, including the header and footer
        }
      ],
      genteGuay: [
        { id: 0 + 1, nombre: 'Jaime', edad: 28 },
        { id: 1 + 1, nombre: 'Dian', edad: 22 },
        { id: 2 + 1, nombre: 'Ramon', edad: 28 },
        { id: 3 + 1, nombre: 'Antonio', edad: 72 },
        { id: 4 + 1, nombre: 'Mati', edad: 70 },
        { id: 5 + 1, nombre: 'Guata', edad: 29 },
        { id: 6 + 1, nombre: 'Juanmi', edad: 23 },
        { id: 7 + 1, nombre: 'Abuela', edad: 94 },
        { id: 8 + 1, nombre: 'Lobezno', edad: 269 },
        { id: 9 + 1, nombre: 'Jesús', edad: 2019 },
        { id: 10 + 1, nombre: 'Noe', edad: 4000 }
      ]
    }
  },
  computed: {
    rows() {
      return this.genteGuay.length
    }
  },

  methods: {
    edadGente(arr) {
      // Set slice() to avoid to generate an infinite loop!
      return arr.slice().sort(function(a, b) {
        return a.edad - b.edad
      })
    }
  }
}
</script>

<style lang="scss" scoped></style>
