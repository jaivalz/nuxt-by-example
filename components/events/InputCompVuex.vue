<template>
  <div>
    <input
      v-model="input"
      :placeholder="placeholder"
      @keyup.enter="monitorEnterKey"
    />
  </div>
</template>

<script>
export default {
  props: {
    placeholder: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      input: ''
    }
  },

  methods: {
    monitorEnterKey() {
      this.$store.dispatch('addNote', this.input)
      this.$store.dispatch('addTimestamp', new Date().toLocaleString())
      this.input = '' // set input field back to blank
    }
  }
}
</script>

<style lang="scss" scoped></style>
