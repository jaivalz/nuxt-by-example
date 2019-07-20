<template>
  <div class="container">
    <div class="user_friends">
      <h1>Aqui estamos los friends</h1>
      <br />
      <ul>
        <li v-for="(friend, index) in friends" :key="index">
          {{ friend }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      friends: ['Ray', 'Jai', 'Danay']
    }
  }
}
</script>

<style scoped>
.user_friends {
  border: 1px solid green;
  padding: 10px 20px;
}
</style>
