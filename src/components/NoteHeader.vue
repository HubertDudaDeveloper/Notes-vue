<template>
    <div class="header">
        <img class="header__img" src="./../assets/logo.png">
        <button class="header__button" @click="createNote()">Dodaj Notatkę</button>
        <button class="header__button" @click="deleteNote()">Usuń Notatkę</button>
    </div>
</template>
<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default Vue.extend({
  name: 'NoteHeader',
  methods: {
    createNote () {
      const note = { id: '', title: 'Nowa Notatka', content: '' }
      this.$store.state.note.push(note)
    },
    deleteNote () {
      this.$store.state.note.splice(this.$store.state.currentKey, 1)
    }
  }
})

</script>
<style scoped lang="scss">
.header {
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 50px;
    &__img {
        padding: 0px 50px;
        height: 100px;
    }
    &__button {
        height: 50px;
    }
}
@media screen and (min-width: 800px) {
    .header {
      flex-direction: row;
    }
  }
</style>
