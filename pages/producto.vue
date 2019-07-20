<template>
  <div>
    <div v-for="(producto, index) in productos" :key="index">
      <producto-sano :nombre="producto.nombre">
        <template slot="blueface">
          <h3>El producto es el {{ producto.nombre }}</h3>
          <h3>La categoría es {{ producto.categoría }}</h3>
          <h3>It has {{ producto.conexion }} connection</h3>
          <br />
          <img
            src="https://st.forocoches.com/foro/customavatars/avatar810072_1.gif"
            alt=""
            @click="
              handleClick(
                'has hecho click en la imagen de' + ' ' + producto.nombre
              )
            "
          />
        </template>
        <template slot="think">
          <img
            src="https://st.forocoches.com/foro/customavatars/avatar810072_1.gif"
            alt=""
          />
          <br />
          <h5>El producto es el {{ producto.nombre }}</h5>
          <p>La categoría es {{ producto.categoría }}</p>
          <span>It has {{ producto.conexion }} connection</span>
        </template>
      </producto-sano>
    </div>
  </div>
</template>

<script>
import ProductoSano from '@/components/ProductoSano.vue' // Importo al componente button

export default {
  components: {
    ProductoSano
  },
  data() {
    return {
      productos: [
        {
          nombre: 'Termostato Blueface',
          categoria: 'Termostato',
          conexion: 'wired'
        },
        {
          nombre: 'Termostato Think',
          categoria: 'Termostato',
          conexion: 'wired'
        },
        {
          nombre: 'Termostato Think',
          categoria: 'Termostato',
          conexion: 'wireless'
        },
        {
          nombre: 'Webserver Wired',
          categoria: 'Webserver',
          conexion: 'wired'
        },
        {
          nombre: 'Webserver Wireless',
          categoria: 'Webserver',
          conexion: 'wireless'
        }
      ]
    }
  },

  methods: {
    handleClick(text) {
      alert(text)
    }
  }
}
</script>

<style lang="scss" scoped></style>
