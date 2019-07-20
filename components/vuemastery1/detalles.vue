<template>
  <div>
    <ul>
      <li v-for="(detail, index) in details" :key="index">{{ detail }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    detalles: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      details: ['80% cotton', '20% polyester', 'Gender-neutral']
    }
  }
}
</script>

<style scoped></style>
