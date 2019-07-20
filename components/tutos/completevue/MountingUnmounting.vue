<template>
  <div class="container">
    <h1>Ejemplo props</h1>
    <div>
      <h2>Hey</h2>
      <br />
      <p>Me llamo {{ username }}</p>
      <p>Me apellido {{ userlastname }}</p>
      <p>Tengo {{ userage }} años</p>
      <br />
      <h3>Parents</h3>
      <div v-for="(key, value, index) in userparents" :key="index">
        <p>{{ key }}</p>
        <p>{{ value }}</p>
      </div>
      <button @click="updateName">Update name</button>
      <button @click="updateLastName('Smith')">Update lastname</button>
      <br />
      <div>
        <input v-model="freindInput" type="text" />
        <button @click="addFriend">Add friend</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    username: {
      type: String,
      default: ''
    },
    userlastname: {
      type: String,
      default: ''
    },
    userage: {
      type: Number,
      default: 19
    },
    userparents: {
      type: Object,
      default: null
    },
    updateLastName: {
      type: Function,
      default: () => {}
    }
  },
  data() {
    return {
      friendInput: ''
    }
  },
  methods: {
    updateName() {
      // this.name = 'Jaime el mejor vale o que tronco'
      this.$emit('updateName', 'Francis Steve')
    }
  },
  addFriend() {}
}
</script>

<style lang="scoped"></style>
