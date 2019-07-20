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
      this.$bus.$emit('add-note', {
        note: this.input,
        timestamp: new Date().toLocaleString()
      })
      this.input = ''
    }
  }
}
</script>

<style lang="scss" scoped></style>
