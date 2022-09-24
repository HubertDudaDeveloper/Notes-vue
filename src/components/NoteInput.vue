<template>
    <div class="container">
        <input class="input" placeholder="Tytuł" v-model="$store.state.note[$store.state.currentKey].title">
        <textarea class="input" placeholder="Notatka" v-model="$store.state.note[$store.state.currentKey].content"></textarea>
    </div>
</template>
<script>
import Vue from 'vue'
import Vuex from 'vuex'

export default Vue.extend({
  name: 'NoteInput'
})

</script>
<style scoped lang="scss">
.container {
    display: grid;
    grid-template-rows: 1fr 10fr;
    gap: 50px;
    .input {
        padding: 20px;
        border-radius: 25px;
    }
}
</style>
