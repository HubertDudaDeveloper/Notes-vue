<template>
    <div class="header">
        <img class="header__img" src="./../assets/logo.png">
        <button class="header__button" @click="createNote()">Dodaj Notatkę</button>
    </div>
</template>
<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default Vue.extend({
  name: 'NoteHeader',
  data () {
    return {
    }
  },
  methods: {
    createNote () {
      const note = { id: '', title: '', content: '' }
      this.$store.state.note.push(note)
    }
  }
})

</script>
<style scoped lang="scss">
.header {
    display: flex;
    align-items: center;
    gap: 50px;
    &__img {
        padding: 0px 50px;
        height: 100px;
    }
    &__button {
        height: 50px;
    }
}
</style>
