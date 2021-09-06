<template>
<the-navbar></the-navbar>
  <div class="container with-nav">
    <div class="card">
      <h1>Про Vuex</h1>
      <h2>Счетчик {{ counter }}  ({{ doubleCounter }})</h2>
      <button class="btn primary" @click="add">Добавить</button>
      <button class="btn danger"  @click="incrementAsync({value: 10, delay: 200})">Добавить 10</button>
    </div>
  </div>
</template>

<script>
import {mapGetters, mapActions} from 'vuex'
import TheNavbar from './TheNavbar.vue'

export default {
    computed: {
      ...mapGetters(['counter', 'doubleCounter'])
    },
    methods: {
      add() {
        // this.$store.commit('add', 1)
        this.$store.commit({
          type: 'add',
          value: 1
        })
      },
      ...mapActions(['incrementAsync']),
      // incrementAsync() {
      //   this.$store.dispatch('incrementAsync', {
      //     value: 10,
      //     delay: 200
      //   })
      // }
    },
  components: {TheNavbar}
}
</script>
