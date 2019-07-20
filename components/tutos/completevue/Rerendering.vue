<template>
  <div>
    <div class="container">
      <h2>Rendering and Re-rendering</h2>
      <p>Voy a hacer que el nombre cambie</p>
      <h3>{{ name }}</h3>
      {{ update() }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Jaime'
    }
  },
  methods: {
    update() {
      setTimeout(() => {
        this.name = 'Jaimocho'
      }, 2000)
    }
  }
}
</script>

<style lang="scss" scoped></style>
