<template>
  <div id="app">
    <NoteHeader />
    <main class="note">
      <NoteNav :note="note"/>
      <NoteInput />
    </main>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Vuex from 'vuex'
import NoteNav from './components/NoteNav.vue'
import NoteInput from './components/NoteInput.vue'
import NoteHeader from './components/NoteHeader.vue'

export default Vue.extend({
  name: 'App',
  data () {
    return {
      note: []
    }
  },
  components: {
    NoteHeader,
    NoteNav,
    NoteInput
  }
})
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.note {
  display: grid;
  grid-template-columns: 1fr 3fr;
  padding: 50px 0px;
}
</style>
