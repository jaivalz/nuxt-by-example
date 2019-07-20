<template>
  <div>
    <br />

    <b-container>
      <b-row>
        <b-col cols="12" md="6"
          ><img
            src="https://fotos00.farodevigo.es/2017/02/26/328x206/juan-ramon.jpg"
            alt=""
        /></b-col>

        <b-col cols="12" md="6">
          <h5 v-if="nombre === 'Termostato Blueface'" class="text-primary">
            <slot name="blueface"></slot>
          </h5>
          <h5 v-else-if="nombre === 'Termostato Think'" class="text-primary">
            <slot name="think"></slot>
          </h5>
          <h5 v-else class="text-primary">
            <slot name="blueface"></slot>
          </h5>

          <!-- <br />
          <p class="text-secondary text-md-justify">
            Plénum motorizado Medium Airzone con cuello para la adaptación
            mecánica a las principales unidades de conductos Aermec. El plénum
            motorizado Medium Airzone incluye: Central del sistema, encargada de
            hacer la gestión del sistema, mediante dispositivos cableados e
            inalámbricos. Pasarela de comunicación. Compuertas circulares de 200
            mm de diámetro. Sistema de regulación manual de caudal. Variación de
            hasta ±3 dB(A) sobre el nivel de presión sonora de la unidad
            interior y peso máximo 18 Kg.
          </p> -->
        </b-col>
      </b-row>
    </b-container>

    <br />
  </div>
</template>

<script>
export default {
  props: {
    nombre: {
      type: String,
      default: null
    },
    categoria: {
      type: String,
      default: null
    },
    conexion: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped></style>
