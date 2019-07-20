<template>
  <div class="container">
    <div><h1>The complete VUE js Developer Course</h1></div>
    <hr />
    <rerendering></rerendering>
    <hr />
    <br />
    <computed-watchers></computed-watchers>
    <hr />
    <br />
    <mounting-unmounting
      :username="name"
      :userlastname="lastname"
      :userage="age"
      :userparents="parents"
      :update-lastname="updateLastName"
      @updateName="name = $event"
    ></mounting-unmounting>
    <br />
    <friends></friends>
    <br />
  </div>
</template>

<script>
import Rerendering from '@/components/tutos/completevue/Rerendering.vue' // Importo al componente button
import ComputedWatchers from '@/components/tutos/completevue/ComputedWatchers.vue' // Importo al componente button
import MountingUnmounting from '@/components/tutos/completevue/MountingUnmounting.vue' // Importo al componente button
import Friends from '@/components/tutos/completevue/Friends.vue' // Importo al componente button

export default {
  components: {
    Rerendering,
    ComputedWatchers,
    MountingUnmounting,
    Friends
  },
  data() {
    return {
      name: 'Eladio',
      lastname: 'Sevilla',
      age: 25,
      parents: {
        mother: 'Juliana',
        father: 'Peibol'
      }
    }
  },
  methods: {
    updateLastName(value) {
      this.lastname = value
    }
  }
}
</script>

<style lang="scss" scoped></style>
