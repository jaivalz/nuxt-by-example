/* eslint-disable no-console */ /* eslint-disable no-console */
<template>
  <div>
    <div class="container">
      <h2>Computeds and Watchers</h2>
      <input v-model="user" />
      <button @click="toggleActive">Other action</button>
      <br />
      <div>Name: {{ compMessage }}</div>
      <div>Active: {{ isActive() }}</div>
      <div>Loading: {{ loading }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: '',
      active: false,
      loading: false
    }
  },
  computed: {
    compMessage() {
      return this.user === 'Francis' ? 'Welcome' : 'Not allowed'
    }
  },
  watch: {
    active(value) {
      this.loading = true
      setTimeout(() => {
        this.loading = false
      }, 3000)
    }
  },
  methods: {
    isActive() {
      return this.active ? 'Active' : 'Not Active'
    },
    toggleActive() {
      this.active = !this.active
    }
  }
}
</script>

<style lang="scss" scoped></style>
