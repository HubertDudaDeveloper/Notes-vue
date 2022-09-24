<template>
    <div class="nav">
          <button v-for="(item, index) in $store.state.note" :key="index" @click="keySelect(index)">{{ item.title }}</button>
    </div>
</template>
<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default Vue.extend({
  name: 'NoteNav',
  methods: {
    keySelect (key) {
      this.$store.state.currentKey = key
    }
  }
})

</script>
<style>
</style>
