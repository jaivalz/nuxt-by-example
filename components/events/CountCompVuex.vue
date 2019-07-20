<template>
  <div>
    <p>Contador sano: {{ noteCount }}</p>
  </div>
</template>

<script>
export default {
  computed: {
    noteCount() {
      return this.$store.getters.getNoteCount
    }
  }
}
</script>

<style lang="scss" scoped></style>
