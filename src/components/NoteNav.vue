<template>
    <div class="nav">
        <ul>
            <li v-for="(item, index) in $store.state.note" :key="index"><button @click="keySelect(index)">{{ item.title }}</button></li>
        </ul>
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
  },
  data () {
    return {
    }
  }
})

</script>
<style>

</style>
