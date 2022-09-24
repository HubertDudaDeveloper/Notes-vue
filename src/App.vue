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

// this.$store.state.note[this.$store.state.currentKey].title
//      localStorage.notes = JSON.stringify(newNotes)

export default Vue.extend({
  name: 'App',
  components: {
    NoteHeader,
    NoteNav,
    NoteInput
  },
  computed: {
    notes () {
      return this.$store.state.note
    },
    title () {
      return this.$store.state.note[this.$store.state.currentKey].title
    },
    content () {
      return this.$store.state.note[this.$store.state.currentKey].content
    }
  },
  mounted () {
    if (localStorage.notes) {
      this.$store.state.note = JSON.parse(localStorage.notes)
    }
  },
  watch: {
    notes (newNotes, oldNotes) {
      localStorage.notes = JSON.stringify(this.$store.state.note)
    },
    title (newNotes, oldNotes) {
      localStorage.notes = JSON.stringify(this.$store.state.note)
    },
    content (newNotes, oldNotes) {
      localStorage.notes = JSON.stringify(this.$store.state.note)
    }
  }
})
</script>

<style lang="scss">
html {
  background-color: #1f1f25;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  font-size: 1.25em;
  margin-top: 60px;
}
.note {
  display: grid;
  padding: 50px 0px;
}
button {
    all: unset;
    width: 50%;
    border: 2px rgb(28, 183, 103) solid;
    border-radius: 10px;
    padding: 15px;
    margin: 5px;
    cursor: pointer;
    &:hover {
      background:rgb(28, 183, 103);
    }
  }

  @media screen and (min-width: 800px) {
    .note {
      grid-template-columns: 1fr 3fr;
    }
  }
</style>
