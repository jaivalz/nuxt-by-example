<template>
  <div>
    <p>Contador sano: {{ noteCount }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      noteCount: 0
    }
  },
  created() {
    this.$bus.$on('add-note', event => this.noteCount++)
  }
}
</script>

<style lang="scss" scoped></style>
