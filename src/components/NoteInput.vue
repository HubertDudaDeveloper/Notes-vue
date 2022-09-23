<template>
    <div class="container">
        <input placeholder="Tytuł" v-model="$store.state.note[$store.state.currentKey].title">
        <textarea placeholder="Notatka" v-model="$store.state.note[$store.state.currentKey].content"></textarea>
    </div>
</template>
<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default Vue.extend({
  name: 'NoteInput',
  prop: {
    key: ''
  },
  data () {
    return {
      title: '',
      content: ''
    }
  }
})

</script>
<style scoped lang="scss">
.container {
    display: grid;
    grid-template-rows: 1fr 10fr;
    gap: 50px;
    input {
        padding: 20px
    }
}
</style>
